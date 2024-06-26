---
title: I Made My First Grep Command
date: 2018-03-02
lastmod: 2019-10-29
description: I finally found a use case for grep
tech: [grep, bash]
projects: [virtual-jo]
draft: false
---

For my senior project, I'm working on a voice-powered lab assistant for my college's CS department. Among the assistant's tasks is getting menu information from the college cafeteria (the Mensa). So basically, a user should be able to ask something like

> What's for dinner in the Mensa tomorrow?

or

> When does the Mensa next serve Chicken Cordon Bleu?

While doing the first is easy, the second one needed more time. The time-consuming aspect was trying to scrape all the possible food items from the Mensa's menu page because

* I had to collect records for 200ish days
* Some food items repeat
* Sometimes the menu has notes to look out for
* Sometimes menu items express the same thing and state them differently ("white and wheat rolls" vs "wheat and white rolls")

After spending a considerable amount of time crafting a Node.js script to collect the menu pages, I needed to pick out the food items. 

For the most part, the food items were represented in lists, like this

```html
<p>
    <b>Breakfast</b>
    <ul>
        <li>Hard Boiled Eggs</li>
        <li>Design Your Own Omlette</li>
        <li>American Fries</li>
        <li>Fruit Salad</li>
        <li>Malt-O-Meal</li>
    </ul>
    <p>...
```

Not the best HTML, but at least I could extract the menu items by taking the contents of every list element.

Up to this point, I was using [`cheerio.js`](https://github.com/cheeriojs/cheerio) a jQuery implementation for Node.js, allowing you to parse HTML and select and manipulate the DOM.

I was going to make a loop for each webpage and save all the scraped foods into a separate file, but then I thought about [`grep`](https://www.gnu.org/software/grep/manual/grep.html).

While I've never used `grep`, I know it's used for searching for text in files. After [a](https://stackoverflow.com/questions/13566574/how-to-match-content-between-html-specific-tags-with-attribute-using-grep) [little](https://unix.stackexchange.com/questions/276741/using-grep-and-looking-for-unique-occurrences) [googling](https://www.gnu.org/software/grep/manual/grep.html) (While writing this, I realized that I could have used `man grep` 🤦🏾), I found created a bash command that will pull out all the list items in all the files, remove some items, sort the file, remove duplicates and save it in a file. Here it is.

```bash
$ grep -hoP '(?<=<li>).*?(?=</li>)' * | sed "s/(RFH.*)$//g" |sort --unique > ../foods.txt
```

Let's go through it piece by piece.

* `grep -hoP '(?<=<li>).*?(?=</li>)' *`
    * `grep` - The utility responsible for searching files
    * `-hoP`- configuration for grep. `h` tells grep to omit the file name from the result so I just have the match. `o` tells grep to only print the matching text instead of the context around it as it usually would. `P` means use Perl regular expressions. Note that these flags are case sensitive.
    * `'(?<=<li>).*?(?=</li>)'` - The regular expression that matches the contents within `<li>` tags. `(?<=<li>)` and `?(?=</li>)` are the [*positive lookarounds*](https://www.regular-expressions.info/lookaround.html) which essentially means that the expression should look for these elements, but not match them (that is, look for stuff between these). `.*` means that it will look for any number of (`*`) any characters (`.`). Basically, this expression means "match the contents of the `<li>` HTML elements".
    * `*` is the thing we want to grep, in this case, the current directory containing the menu forms.
* `|` - this is a pipe command, which tells bash to pass the output of the previous command (grep), to the next command.
* `sed "s/(RFH.*)$//g"`
    * `sed` - [sed](https://www.gnu.org/software/sed/manual/sed.txt) is a <span style="font-weight:bold">s</span>tream <span style="font-weight:bold">ed</span>itor. Simply put, it parses and edits text in files.
    * `"s/(RFH.*)$//g"` - This means substitute (`s/`) anything matching `(RFH.*)`for nothing (`//`) across the entire file (globally, `g`)
* Another `|` which pipes sed's result to `sort`
* `sort --unique`
    * [`sort`](http://man7.org/linux/man-pages/man1/sort.1.html) does what it says on the tin, sorts the lines in a file alphabetically
    * `--unique` collapses duplicate lines into one, ensuring that every line has unique values.
* `> ../foods.txt` means instead of writing the output to the file, write the results to the file called `../food.txt`. __Note that this overwrites the prior contents of the file__.

And there it is, 14 lines of code put into one. These 14 lines to be exact.

```js
const cheerio = require("cheerio"); // Extract HTML
const fs = require("fs"); // File System
menu_items = new Set(); // Ensures unique elements are added

let files = fs.readdirSync("."); //read current directory (synchronously)
files.forEach((file, i) => {
    // for each element
    data = fs.readFileSync(file); //get the file's contents
    let $ = cheerio.load(data); //build a DOM using cheerio
    $("li").each((i, elem) => {
        // add each list item to the set
        menu_items.add($(elem).text());
    });
})
menu_items = Array.from(menu_items); //turn the set to an array
fs.writeFileSync("food.txt", menu_items.join("\n")); //write the list items to a file
```

I think it's really cool that bash provides all of these utilities. I remember reading the book [The Linux Command Line by William Shotts](http://www.linuxcommand.org/) which looks into how the Linux Command Line works. I don't think I finished it but I had so much fun reading it. I'll read it again and let you guys know what I feel about it.
