The Goal of this repo is:
1. to document the internals of the Deity BP-TRX (assuming many similarities to the BP-TX) for repair and battery replacement purposes and
2. document the firmware for possible reverse engineering modification and adding of features. Some features I have dreamed up:

   a. support MP3/M4a/Ogg recording formats internally

   b. Disable self monitoring in interface mode

   c. Explore VoIP capabilities over network adapter or WiFi?

Full Photo album here: https://imgur.com/a/UUb3bIW

Let's start with a teardown. You will need the following:

-Torx T-5 screwdriver

-small philips head screwdriver
-Needle nose tweezers (available inexpensively as watchmaking tools)
-pliers

Step 1. Preparation:

Remove SD Card

Remove belt clip

Unscrew the external torx screws, 2 matching on the front and 2 on the back with self tapping tips, 2 on the "bottom face" (where USB port is) that are machine screws

Remove the 3 nuts around the headphone jacks and SMA port. Needlenose tweezers fit into the two holes opposing the headphone jack and spin counterclockwise to remove.

Step 2. CAREFULLY begin to slide out the plastic side caddy from the metal housing. Some slight lifting of the front metal helps this process.

Step 3. Remove the 3 screws around the exterior of the board (the bottom middle two are part of the USB assembly and can stay in)

Step 4. Remove board from plastic caddy while keeping SMA assembly wire loose.

Step 5. Heat battery until it can be easily separated from board with a credit card (took me about 5 minutes on a heated blanket, so hair dryer would definitely work)

Battery Text Reads:

AP158 3.7V(10.36Wh)

4.2V 2800mAh

Step 6. Reassemble using this process backwards, be VERY careful with wires protruding from board when sliding metal chassis back on


Firmware analysis

binwalk -Me /Users/andrewlogan/Downloads/Deity\ Connect\ BP-TRX\ V1.5/Deity_BP_TRX_Update.bin 

Scan Time:     2024-07-29 22:26:14
Target File:   Deity Connect BP-TRX V1.5/Deity_BP_TRX_Update.bin
MD5 Checksum:  19d18953ece43c9edc11b9a08bdb34ca
Signatures:    411

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
208932        0x33024         CRC32 polynomial table, little endian
726656        0xB1680         CRC32 polynomial table, little endian

Opening in a hex editor reveals plain text menu items
