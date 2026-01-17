# DOSu-
DOSu! is an open source engine heavily inspired by the game "osu!" made entirely in C89 and running natively under MS-DOS operating systems.

--HOW TO GET STARTED--
Inside the src folder you find the source code both for DOSu! and DOSu!_demo wich is a version made primarily for demonstrations since it plays autonomously.
Inside the bin folder you will find the already compiled EXE files of both programs.

--DEMO/AUTOPLAY--
The Dosu!_demo allows you torun the beatmap and the audio without playing the game by yourself, ideal for demonstrations and
lower end hardware testing, to run the program the same files are required as for the normal EXE file.

--AUDIO SETUP--
DOSu! is acessing audio through sound blaster or compatible card on address 0x220 IRQ 5 and DMA 1
by default. You can changes those settings in the #define piece of the source code if you wish so.
DOSu! expects the audio as "audio.wav" file placed in the same directory as the EXE. The format should be 8-bit mono PCM
with the sample rate being variable but is tested with 8khz.

--BEATMAP SETUP--
DOSu! natively supports osu! v14 beatmaps all you need to do is take your desired beatmap and rename it to "map.osu" and
place it in the same directory as the EXE but i recommend not harder than 2 or 3 star maps being used as the engine in its current 
state is not very optimized and more objects would cause significant performance drops.

--BGI (IMPORTANT!)--
DOSu! by default expects the bgi folder to be located in C:\TC\BGI but the adress can be modified within the code
but requires some digging in the source code. For quick search i recommend opening the code in a text editor that is
capable of searching words and search "initgraph" wich will lead you to the lines where the path is also located written
as "C:\ \TC\ \BGI".  Dont forget to use double slashes in the path as single slashes might cause some chaos in the c89 style code,
depends on wich compiler you are using (i used the original Turbo C++ 3.0).

--SCORING AND TIMING--
The scoring and timing within the EXE is currently pretty improvised but most of those settings can
be changed in the #define section of the code like the player health, windows in wich you get 300, 100 or 50 points in milliseconds.

--CONTROLS--
By default you use the mouse to move the cursor wich is a small yellow circle. To hit you might use the left mouse button or
the X key on your keyboard. 

--SLIDERS AND SPINNERS--
Spinners are currently not implemented and are being ignored.

Sliders are implemented but experience a lot of issues with timing by wich i mean that
they all are being on the screen for the same time wich means you can use smaller sliders but longer ones would
disappear before you could finish the trajectory so as a fallback a slightly different mechanism is implemented, 
basically all you need to do is hit and hold it as a slider but you dont slide all the way through the
trajectory but you just symbolically move your cursor in the way the slider continues to atleast somehow
mimic the slider mechanics

--LANGUAGE--
Im sorry for this but the program is basically a mishmash of English and Czech language but even though its understandable.

--SYSTEM REQUIERMENTS--
The Dosu! is tested on a Pentium II machine and the engine has some optimization struggles but
with some tweaking like how many seconds ahead objects show up you can drastically improve the performance and i have no
doubt it can run on older processors, theoretically the original Pentium and older if some optimizations were made within the engine.
to change how many miliseconds ahead objects show, view the "#define PRE_SHOW" in the source code, defeault is 2000 miliseconds

From the storage perspective the engine itself is tiny and most of your storage space would be used up by the WAVE audio but i recommend atleast
10 megabytes of storage for comfortable use but if you can shrink the audio file and would have one map only then you can probably fit it on a 3.5 inch floppy disk
without bigger issues.

For the RAM memory i think you could theoretically even run it in the DOS defeault 640KB but i did not test it.

--YOUR INPUT IS WELCOME--
This project from its roots was made as open-source and everybody is welcome to contribute to it.
If you want something a different way, go ahead you are absolutely free to modify the engine in any possible way you want and
if you have any suggestions or questions, contact me on my gmail: janhelan24@gmail.com
