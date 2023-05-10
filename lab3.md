# Lab  3<br/>
I found interesting command-line options for command `find`. <br/><br/>
  1. First option is `-type`. It can find file, directory, or other things based on the input.<br/>
`-type f` finds and returns files. `-type d` finds and returns the directory. <br/>
     * Example of using `-type f` <br/>
     ![fname](https://raw.githubusercontent.com/hojun01720/cse15l-lab-reports/main/f-name.png) <br/>
     It finds all the files that ends with "t.txt" under the `stringsearch/stringsearch-data/technical/*` directories <br/><br/>
     * Example of using `-type d` <br/>
     ![dname](https://raw.githubusercontent.com/hojun01720/cse15l-lab-reports/main/d-name.png)<br/>
     It finds all the directory that ends with "s" under the `stringsearch/stringsearch-data/technical/*`<br/><br/><br/>
  2. Second option is `-name`. As shown above, it can find the files or directories that ends with certain letters or words.<br/>
  `-name "<letters that ends with>"` <br/>
     * Example of using `-name` for files <br/>
     ![fnamestars](https://raw.githubusercontent.com/hojun01720/cse15l-lab-reports/main/f-name-stars.png)<br/>
     As it is shown, after the command multiple `*` can be written to find files. Format `*-*.*.txt` only matches with files `chapter-13.*.txt`.
     * Use of `-name` for directories <br/>
     ![dnotname](https://github.com/hojun01720/cse15l-lab-reports/blob/main/d-not-name.png?raw=true) <br/>
     `-not` makes the command to 'not' find the directories that ends with 't'
