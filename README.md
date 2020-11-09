# aduroh2-openhab2.5.x
Implemented Aduro H2 Pellet Oven in OpenHab 2.5.x with NBE pellet burner V7/V13 UDP protocol test client

This project contain example files for an OpenHab 2.5.x implementation of monitoring and controlling an ADURO H2 pellet oven, using the NBEtest tool from motoz.

The project is use-as-is and inspirational-only for potential users. I offer no support. The rules file is the key to the setup - and my rules could most certainly be coded better - but this works for me and I have limited time to polish ;-)

Steps to take for you to re-use:
1. Note the serial# and password of your pellet oven. These will be located on a sticker on the inside of the bottom door of your oven (the big front door you open to fill pellets).

2. Implement NBEtest tool on the same linux server where you are running OpenHab 2.5.x. For installation instructions see here:
NBE pellet burner V7/V13 UDP protocol test client (https://github.com/motoz/nbetest)

3. Check that your NBEtest tool will give you data from your ADURO pellet oven by trying a few examples in linux (see read-me from motoz in step 2) - and check that it works with and without password ("Set" command needs password. "Get" does not).

4. Move the OpenHab example files to the respective folders in your OpenHab installation.

5. Update the whitelist file and the things-file with your own serial# and password (see step 1).

6. Test, adapt and enjoy

In my setup, I see that occasionally the nbetest commands does not give OK or the relevant output - but rather an error (output starts with the word TRACEBACK...". I dont know why this is the case, but I have implemented re-issue of the commands when this happens, and that seem to work.

My configuration requests updated data (3 data streams; operational data, setboiler data and logentries) every minute. This cycle can be reduced to 5 or 10 minutes, but will of course reduce the actuality and response time of the oven to your commands. Every minute seem to work OK.
