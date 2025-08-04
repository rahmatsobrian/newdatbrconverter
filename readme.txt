How To Convert system.new.dat.br to system.img (or vendor file) on Termux Android No Root Needed

This only to convert new.dat.br to new.dat to .img For the other way around, sorry I don't know

#Step

1. Install git & brotli package
Command: pkg install git && pkg install brotli

2. Clone this repo
git clone https://github.com/rahmatsobrian/newdatbrconverter && cd newdatbrconverter

Put the file:
system.new.dat.br
system.patch.dat
system.transfer.list
vendor.new.dat.br
vendor.patch.dat
vendor.transfer.list
into this folder (newdatbrconverter)

3. Convert system.new.dat.br to system.new.dat
Command: brotli --decompress system.new.dat.br -o system.new.dat

Before: system.new.dat.br (500Mb) After/Result: system.new.dat (1,5Gb)

4. Convert vendor.new.dat.br to vendor.new.dat
Command: brotli --decompress vendor.new.dat.br -o vendor.new.dat

Before: vendor.new.dat.br (100Mb)
After/Result: vendor.new.dat (300Mb)

5. Convert system.new.dat to system.img
Command: python sdat2img.py system.transfer.list system.new.dat system.img

Before: system.new.dat (1,5Gb)
After/Result: system.img (3Gb)

6. Convert vendor.new.dat to vendor.img
Command: python sdat2img.py vendor.transfer.list vendor.new.dat vendor.img

Before: vendor.new.dat (300Mb)
After/Result: vendor.img (500Mb)

#Done

The main thing is, We first change system.new.dat.br to system.new.dat and then lastly we change it to system.img, same for vendor file

Example estimated file size (I decompressed system.new.dat.br and vendor.new.dat.br in nusantara rimuru rom for rolex device/Redmi 4A)

System.new.dat.br: 500Mb System.new.dat: 1,5Gb
System.img: 3Gb

Vendor.new.dat.br: 100Mb Vendor.new.dat: 300Mb
Vendor.img: 500Mb

So we can conclude that system/vendor.new.dat.br is system.img compressed/encrypted several times.

If you done, you can extract the .img file with ZArchiver app

Note: if you non root, maybe There are some files that cannot be extracted because they are symbolic link files, so they are just shortcuts. On a rooted phone, I forgot whether it was fully functional or not.

But one thing I know, if you extract the system.img / vendor.img file in the termux directory (By using the img extractor script), all files will be successfully extracted, including the symbolic link file, But if you use ZArchiver, it still won't be able to extract everything, even if you extract it to the Termux folder.

And if you extract it on the internal/memory card, it might not be possible to extract everything like a symbolic link.

Sorry if my words are very confusing, I used Google Translate to write this

I hope this help you :)

Thanks To
-danielmmmm for the python script