Very simple cli mplayer wrapper usefull for viewing serials. 

Place this repo somewhere in **$PATH** and just type in directory with series videos:
```sh
$ anp
```
It list of all videio files in current dir in **./files.list** 
(you can edit it or regenerate using **anp-mkflist**)
and play first of it. Then save played file name in **./cur.txt** and print prompt:
```
Video_00.avi  (1/18) has played
next, current, previous or quit (N/c/p/q)?  
```

When **./files.list** and **./cur.txt** already exists it search **cur** video in **list** and play next.

**Actions:**
* **next** - press 'n' or enter to play next video then save it name in **./cur.txt** and print prompt. 
* **curent** - press 'c' to replay current video and print prompt. 
* **previous** - press 'p' to reset current video to previous and print prompt.
* **quit** - press 'q' to quit.

For use separatly placed subtitles use **anp-mksublist** or just list paths to files in **./sub-files.list**.

To pass additional options to mplayer use **anp-options** or just save  it in **./options.txt**.

**License:** WTFPL

### Commands

#### anp
**Usage:** anp [CUR_FILE]

#### anp-mkflist
Recursive find video files in paths and place result in **./sub-files.list**.
Remove ".part" suffix if exist (it usefull when some files are still downloading).

**Usage:** anp-mkflist [PATH... [FIND_OPTION...]]

#### anp-mksublist
Recursive find subtitle files in paths and place result in **./subs-files.list**.

**Usage:** anp-mksublist [PATH... [FIND_OPTION...]]

All arguments passed to find together with name filter.

```sh
# Examples:
# search in current dir
$ anp-mksublist 
# searh in Subs1 and ../Subbs2 dirs but not in its subdirs
$ anp-mksublist Subs1 ../Subs2 -maxdepth 1
```

#### anp-options
Save it's arguments to **./options.txt**.
