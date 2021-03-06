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

	- `2628857 ` : iNode number
	- `-rwxrwxr-x ` : permissions
	- `1 ` : number of hard links
	- `raghav18gupta ` : owner
	- `raghav18gupta ` : group
	- `61 ` : size (Bytes)
	- `Jan 15 13:25 ` : date modified
	- `git-push.sh` : name

- Soft links are just shortucts.
	- `ln -s file1 softfile`

	![softlink](https://raw.githubusercontent.com/raghav18gupta/shell/master/messed-dir/static_files/softlink1.png)
	
	- Note: 
		- `softfile` is another 'actual' file as it has different iNode number than `file1`.
		- `file1` still has `1` hard link.
		- `l` in `softfile` permission.
	- Hence `file1` contains actual data, while `softfile` is just shortcut of it.
	
	- Rename `file1` to `file2`:

	![softlink](https://raw.githubusercontent.com/raghav18gupta/shell/master/messed-dir/static_files/softlink2.png)

- Hard links are just diffrenet names pointing the same file.
	- `ln file1 hardfile`
		- `file1` has now `2` numbers of hardlinks.
		- if `file1` is deleted or renamed, `hardfile`
		![softlink](https://raw.githubusercontent.com/raghav18gupta/shell/master/messed-dir/static_files/hardlink.png)
	- So there are two "names" `file1` and `hardfile` pointing to same content. Hence they have same iNode value.
	- If we delete `file1`, only name is deleted, not actual file having content. Actual file will delete if we further delete `hardfile`.
	![softlink](https://raw.githubusercontent.com/raghav18gupta/shell/master/messed-dir/static_files/hardlink2.png)
	- Also note that: A directory has atleast `2` numbers of hardlinks beacause it has two name: `.` and it's name.
	- Some OS prevent user to make hardlink of a directory.


