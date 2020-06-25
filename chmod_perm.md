####To determine the mode (or permission settings) of a particular file, use the command

		`ls -lg filename.'

####This will produced string of 10 characters
      (-rwxr-x--x 1 owner group 2300 Jul 14 14:38 filename)
		'-' indicates that the file is a plain file.

		'd' means it is a directory.

(respectively, `r', `w', or `x' if the corresponding permission is turned on for the owner or `-' if the permission is turned off.)

Characters 5-7 similarly show the permissions for the group;

characters 8-10 for all others

The second string shows the number of links that exist to the file.

The third string identifies the owner of the file and the fourth string tells what group the owner of the file is in.


To change the mode of a file, use the chmod command.

	X is any combination of the letters
 	`u' (for owner), `g' (for group), `o' (for others), `a' (for all; that is, for `ugo')

	 Following are some examples:

	chmod u= rx file       (Give the owner rx permissions, not w)

      	chmod go-ls rwx file   (Deny rwx permission for group, others)

     	chmod g+w file         (Give write permission to the group)

     	chmod a+x file1 file2  (Give execute permission to everybody)

     	chmod g+rx,o+x file    (OK to combine like this with a comma)
