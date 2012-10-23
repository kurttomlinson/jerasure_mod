./encoder inputFile #dataFiles #redundantFiles codingTechnique GF(2^x)
encoder /home/kurt/SRDFS/Encode/ECE3041.zip 10 4 reed_sol_van 8 500 0 "/kurt/foo/"

This puts the encoded files in "~/SRDFS/Scatter". If the input file is called "ECE3041.zip", then data files will be called "ECE3041_kX.zip" where X is the file's number. Redundant data files will be called "ECE3041_mX.zip" where X is the file's number. Metadata about the file (number of data files, number of redundant files, encoding scheme, field, etc.) is stored in a file called "ECE3041_meta.txt" in "~/SRDFS/Metadata/kurt/foo/ECE3041_meta.txt"

./decoder FullMetadataPath
decoder /kurt/foo/ECE3041.zip

This looks in a subfolder of the current directory called "Coding". If a metadata file called "ECE3041_meta.txt" is found, then the file is decoded. The decoded file is named "ECE3041_decoded.zip".

decode files from "~/SRDFS/Gather"
decode files to "~/SRDFS/Decoded"

encode files from "~/SRDFS/Encode"
encode files to "~/SRDFS/Scatter"
move metadata to "~/SRDFS/Metadata/foo/bar.txt_meta.txt"


IMPORTANT
1)Make sure to update the homepath variable in encoder.c
2)All directory variables are expected to end with a slash (/)