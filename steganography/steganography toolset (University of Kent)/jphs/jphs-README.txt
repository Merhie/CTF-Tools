jphide & jpseek

Hide and Seek for Linux

These two programs let you hide a file in a jpeg file and then
let you recover it later.

There are many similar programs but "jphide" and "jpseek" have
a big advantage over any others I have seen. They distribute the
hidden file in the jpeg so that not only are the visual effects
minimized but also the statistical effects. Simple programs which
store the hidden file in low order bits result in jpeg files which
are so statisticaly different from normal jpeg files that the
hidden file can be recovered with ease.

"jphide" uses the Blowfish algorithm to provide a stream of
pseudo random control bits which determine where to store the
bits of the hidden file. The program asks for a pass phrase to
initialize this stream. Although the hidden file is "encrypted"
by this process I strongly recommend that you encrypt the hidden
file before insertion into the jpeg.

Using jpeg files of about 200Kb, upto 20Kb can be inserted with
minimal visual and statistical effect. Upto about 35Kb is often
possible at the cost of visual and/or statistical effects. The 
program will refuse to insert even more because it is just too
obvious in the resulting jpeg file.

Note that if the original jpeg file is available then a hidden
file can always be detected (but it cannot be extracted without
the pass phrase). Always use originals that you have scanned
yourself and destroy the original afterwards. A reasonable
alternative if you have access to very high quality jpegs is to
make a cropped and lower quality version of about 200 to 300Kb;
again this must be destroyed after making the jpeg containing
the hidden file.
 

Instructions

jphide  input-jpeg-file  output-jpeg-file  file-to-be-hidden

jpseek  input-jpeg-file  output-hidden-file


Building the programs

Get the sources for the jpeg library jpeg-6a.
I got mine from a RedHat cd.

Compile them following the instructions that came with them. 

Check them out - there is a "make test".

Use tar to put the new programs into the directory containing
the standard jpeg-6a sources:

  tar -xzf jphs.tgz

Patch the makefile:

  patch <Makefile.patch

Make the new programs:

  make

Sorry but if you get errors you will have to fix them yourself.

Install "jphide" and "jpseek" in your /usr/local/bin or wherever.


Conclusion

This pair of programs offers you the ability to hide a file in such a
way that you can later deny that the resulting jpeg contains a hidden
file. Always use original scans and destroy them afterwards. Do not
try to hide more than about 10% of the file. If you are paranoid you
can keep jphide and jpseek on a floppy and be prepared to physically
destroy it. It is then even more difficult to prove that you have 
anything other than normal jpegs.

If you decide to improve these programs please make the results
public domain and post them so that others can enjoy them. The security
of your own hidden files does not depend on keeping your modifications
secret.

Revision 0.3  Allan Latham <alatham@flexsys-group.com>

