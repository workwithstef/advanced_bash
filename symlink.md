### What are symbolic links in linux?
1. A symlink is a shortcut to another file.
2. A soft link (also called symbolic link) is a file system entry that points to the file name and location. Deleting the symbolic link does not remove the original
3. If however, the file to which the symbolic link points to is removed, the symbolic link stops working, it is broken
4. As similar to hard links, any changes to the data in either file is reflected in the other

### How do we create a symbolic link?
- ln -s. If we do not include the -s, a hard link will be created
- e.g. `ln -s symlink/important.txt symlink.txt`

### Example of creating a symbolic link
1. Ok lets make a directory first where we will include our file that we want to create a symlink for, then create the file something.txt
2. `mkdir neededfiles` `cd neededfiles` `touch needed.txt`
3. You can either manually insert some text or you can do this through bash! `echo "this is the original text I want" >> needed.txt`
4. We have a path to the code we want. Lets back out of this directory `cd ..`
5. Lets make our symlink!! `ln -s symlink/needed.txt mysymlink.txt` so here we are creating the symlink for our needed.txt called mysymlink.text
6. Now if we run `cat mysymlink.txt` we can see that it is outputting what we had in the original text file. How useful

### What are the uses for a symlink?
1. Symbolic links are used all the time to link libraries and make sure files are in consistent places without moving or copying the original. Links are often used to “store” multiple copies of the same file in different places but still reference to one file.
