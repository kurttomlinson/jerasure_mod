DEMO STEPS
----------
1) Create path "~/SRDFS/Encode".
2) Place file to encode in "~/SRDFS/Encode".
3) Execute:
	encoder README.txt 3 3 reed_sol_van 8 1 0 "/kurt/foo/"
	encoder ECE3041.zip 3 3 reed_sol_van 8 500 0 "/kurt/foo/"
4) Create path "~/SRDFS/Gathered".
5) Copy m pieces of the file from "~/SRDFS/Scatter" to "~/SRDFS/Gathered".
6) Execute
	decoder /kurt/foo/README.txt
	decoder /kurt/foo/ECE3041.zip



INSTALLATION STEPS
------------------
1) Clone jerasure_mod from GitHub to ~/ECE-6102/jerasure_mod/
2) Execute:
	cd ~/ECE-6102/jerasure_mod/Examples
3) Execute:
	make
4) Open ~/.profile in a text editor.
5) Add the line below to the end of the file.
	PATH="$PATH:~/ECE-6102/jerasure_mod/Examples"
6) Log out and log back in.



ENCODER NOTES
-------------
./encoder inputFile #dataFiles #redundantFiles codingTechnique GF(2^x)
encoder ECE3041.zip 10 4 reed_sol_van 8 500 0 "/kurt/foo/"

The input file is expected to be inside ~/SRDFS/Encode. This program puts the encoded files in "~/SRDFS/Scatter". If the input file is called "ECE3041.zip", then data files will be called "ECE3041_kX.zip" where X is the file's number. Redundant data files will be called "ECE3041_mX.zip" where X is the file's number. Metadata about the file (number of data files, number of redundant files, encoding scheme, field, etc.) is stored in a file called "ECE3041_meta.txt" in "~/SRDFS/Metadata/kurt/foo/ECE3041_meta.txt"



DECODER NOTES
-------------
./decoder FullMetadataPath
decoder /kurt/foo/ECE3041.zip

This program needs the full path to the metadata file. It expects the pieces of the file to have been placed in "~/SRDFS/Gather/". The decoded file is placed in "~/SRDFS/Decoded/"



IMPORTANT
---------
1)Make sure to update the homepath variable in encoder.c
2)All directory variables are expected to end with a slash (/)

END OF FILE

