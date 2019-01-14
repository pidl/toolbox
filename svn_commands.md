# svn commands

Free book about svn: [Version Control with Subversion](http://svnbook.red-bean.com/index.en.html "")

## checking out
~~~
svn checkout <url> <dir>		# checkouts a url from a server
svn co <url> <dir>				# short version of previous command
~~~

~~~
svn info                        # information about the working copy
svn info <file>                 # information about a single file or directory
svn info <url>                  # information about a URL
~~~


## update and revert
~~~
svn update                      # updates the working copy (to HEAD)
svn update -r <rev>		        # updates the working copy to an older revision
~~~

~~~
svn revert <file1> <fileN>		# reverts a single files or directory
svn revert --depth=infinity     # reverts everything 
~~~


## committing files
~~~
svn commit						# commits the current state
svn ci				            # short version of previous command
svn commit -m "message"			# commits without opening editor for message
svn commit -F <msg-file>        # commits with message in a file
svn commit <file1> <fileN>		# commit single files
~~~


## rollback
~~~
svn merge -r <rev2>:<rev1> .    # rollback changes from <rev1> to <rev2>
~~~


## log, diff and status
~~~
svn log                         # log files of everything
svn log -r <rev>                # log message of a specific revision
svn log -r <rev1>:<rev2>        # log messages of a specific revision range
svn log -l <count>              # the last <count> log messages
svn log <file1> <fileN>         # log messages of specific files
svn log <url>                   # log messages of a URL
~~~

~~~
svn diff                        # show changes of every changes in the working copy          
svn diff <file1> <fileN>        # show changes of a specific file in the working copy
svn diff -r <rev> <file>        # show changes of the working copy and a specified revision
svn diff -r <r1>:<r2> <file>    # show changes of the working copy and a specified revision range
svn diff -c <rev> <file>        # show changes of a specified revision
svn diff <url1> <url2>          # show changed of two different URLs
~~~

~~~
svn status                      # get changes of working copy
svn status -q                   # get changes of workinh copy and ignores file not under version control
~~~


## add, delete and move files
~~~
svn add <file1> <fileN>			# add single files or directory
svn add --depth=empty <dir>     # add directory without content
svn add * --force               # add everything recursiv
~~~

~~~
svn delete <file1> <fileN>      # mark a file or directoy as deleted
svn delete --force <file>       # force to delete a file with locale changes
svn delete --keep-local <file>  # delete file from repro but keep file in file system
~~~

~~~
svn move <src> <dest>                   # renames a file in repro
svn move <file1> <fileN> <dir>          # moves several file into a sub directory
svn move -m "msg" <src-url> <dest-url>  # move a file in repro (including commit)
~~~


## branching and merging
~~~
svn copy <url-trung> <url-branch>	# create a branche from a url
svn copy <file1> <fileN> <dir>      # copy files to an sub directory
svn copy -r <rev> <url> <url-tag>   # create a tag from an older revision
svn copy <file> <url>               # copy file to remode URL
svn copy <url> <file>               # copy a file from a remode URL
~~~

~~~
svn switch <url>                           # switch working copy to an url
svn switch -r <rev> <url>                  # switch working copy to specific revision
svn switch --relocate <url-old> <url-new>  # relocate location of repro
~~~

~~~
svn merge <url-branche> .           # merge a branche to the current working copy
svn merge -c <rev> <url> <file>     # merge a single file with a specific revsion
~~~

## vim settings for (commit) messages
~~~
export SVN_EDITOR=vim          # vim is used to compose commit messages
export LC_CTYPE=en_US.UTF-8    # unicode is used
~~~

## commands for vim:
~~~
:qw    # close vim an commit changes
:cq    # close vim an cancel commit changes
~~~




	