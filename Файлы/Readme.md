> Based on parallel_file_transfer.py from mautrix-telegram, with permission to distribute under the MIT license
> Copyright (C) 2019 Tulir Asokan - https://github.com/tulir/mautrix-telegram


<h1>Update : </h1>

* add support for floodwaits
* added an example on how it works
* updated to work with the latest telethon version 1.21
* ~~newest update. it's working fine again thanks to tulir's update~~
* ~~abandon all hope. nothing is working~~
* ~~it's actually working now~~
* ~~:D~~ ~~:(~~ :D
* ~~even progress_callbacks ? idk maybe ?~~
* ~~use a different session for downloading because telegram might close the server.~~
* ~~ok broken again. files md5 is wrong and are corrupted~~
* ~~nvm found why. asyncio.wait doesn't return in order so the file isn't being written in correct order.~~
* ~~used asyncio.gather instead which returns in order. not sure if it's the best solution but it's working~~
* ~~using more than 20 workers will cause all of them to stop working (needs more testing with real accounts)~~
* ~~broken if it lives in another dc until lonami fixes it~~
<h1>Notes :</h1>
 

* progress_callbacks are working fine.
* the number of workers is chosen dynamically
* increase the number of workers to increase the speed. (the faster your internet speed the faster you should put the workers).
* if you put the number of workers too hight you'll get floodwaits.
* the file uploaded will always be a bare document without any attributes. you can add attributes to it using utils.get_input_media() and  utils.get_attributes
* if you want it to be even faster make sure to use https://github.com/painor/pyaesni instead of cryptg

<h1> How to use :</h1>

1. Put all of this in a seperate file
2. import download_file and upload_file from it
3. you can use download_file like so 
                await download_file(client, msg.document, file, progress_callback=prog)
4. you can use upload_file like so 
                    r = await upload_file(client, file,progress_callback=prog)
5. file are objects that .read() .write() methods. 
6. Check the example file

