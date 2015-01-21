# svn commands

## checking out
~~~
svn checkout <url> <dir>		# checkouts a url to a optional directory
svn co <url> <dir>				# shout version of previous command
~~~

~~~
svn info
~~~


## update and revert
~~~
svn update                      # updates from the server
svn update <file1> <fileN>		# updates single files
~~~

~~~
svn revert <file1> <fileN>		# revert single files
~~~


## committing files
~~~
svn commit						# commits the current state
svn commit -m 'message'			# commits without opening editor for message
svn commit <file1> <fileN>		# commit single files
~~~


## add end delete files to repro
~~~
svn add <file1> <fileN>			# add single files to svn
svn remove <file1> <fileN>
~~~


## diff

~~~
svn log
~~~

~~~
svn diff
svn diff <file>
~~~

~~~
svn status
svn status -q
~~~

~~~
svn info
~~~


# branching and merging
~~~
svn copy <url-src> <url-des>	# create a branche from a url
~~~

~~~
svn switch
~~~

~~~
svn merge
~~~

	