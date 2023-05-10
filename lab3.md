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
     As it is shown, after the command multiple `*` can be written to find files. Format `*-*.*.txt` only matches with files `chapter-13.*.txt`. <br/><br/>
     * Use of `-name` for directories <br/>
     ![dnotname](https://github.com/hojun01720/cse15l-lab-reports/blob/main/d-not-name.png?raw=true) <br/>
     `-not` makes the command to 'not' find the directories that ends with 't' <br/><br/><br/>
  3. Third option is `-size`. If `-name` was looking for the matching name, this one finds the file by its size. <brl>
     * Use of `-size`. <br/>
     ![size](https://github.com/hojun01720/cse15l-lab-reports/blob/main/f-size.png?raw=true)<br/>
     From `-12k`, `-` means less than, `12` means the number of the size, and `k` means kilobyte. So `-size -12k` means find the files that are less than 12 kilobytes. <br/><br/>
     * Use of `-size` in range. <br/>
     ![sizerange](https://github.com/hojun01720/cse15l-lab-reports/blob/main/f-size-range.png?raw=true)<br/>
     From `+10k`, `+` means greater than. Hence `-size +10k -size -12k` means finding a file that is greater than 10 kilobytes and less than 12 kilobytes. <br/><br/><br/>
  4. The last option is `-delete`. After finding a specific file that I want, if I write `-delete`, then it deletes that file.
     * Use of delete <br/>
     ![del](https://github.com/hojun01720/cse15l-lab-reports/blob/main/f-del.png?raw=true) <br/>
     As shown, before I had a file `/chapter-13.5.txt`. However after I typed `-delete` in the end, when I reran the find command, it shows it's gone. <br/><br/>
     * Use on `-delete` for multiple files <br/>
     ![delmult](https://github.com/hojun01720/cse15l-lab-reports/blob/main/f-del-mult.png?raw=true) <br/>
     `-delete` can also delete multiple files it found. Now all the `/chapter-13.*.txt` files are gone.
