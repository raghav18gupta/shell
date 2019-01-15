# shell


## cat

- `cat filename`	# print content
- `cat file1 file2`	# print content of multiple files
- `car > newfile`	# create file and enter text
- `cat contentfile > blankfile`	# replace content
- `cat contentfile >> blankfile` # append
- `cat f1 f2 > blankfile`	# merge two file content, store in newfile

## Links: Hard and soft

- Various field in `ls -li`
	![ls -l](https://raw.githubusercontent.com/raghav18gupta/shell/master/messed-dir/static_files/ls-li.png)
	`2628857 ` : inode number
	`-rwxrwxr-x ` : permissions
	`1 ` : number of links pointing to this file
	`raghav18gupta ` : user
	`raghav18gupta ` : group
	`61 ` : size (Bytes)
	`Jan 15 13:25 ` : date creted
	`git-push.sh` : name

- Soft links are just shortucts.
- Hard links are just diffrenet names for the same file.