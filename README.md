# PN532ExtAntNFCBreakout
Arduino compatible PN532 breakout board with support for external antenna. Designed with the xNT implantable chip in mind.
# Why this is here
I created this project because there was a lack of boards availiable online that featured the pn532 without having a huge internal antenna built in. These antennas arent ideal for use with a chip such as the xNT implantable chip, becasue you can only get a read in the "sweet spots" around the corners or directly on the traces, due to its small size. With this board, you can connect your own external antenna via UFL connector, allowing you to connect antennas that are able to work much better with implantable chips. This board and antenna will allow you to make your xNT projects much more compact and reliable, as well as allowing you to extend the antenna away from the controller using a coax cable.

Hopefully this could transform into a board that will help people make better projects to use with their xNT much more easily.

#What it is
##The circuits
The current design is based around (and copied from) The [Keyduino](https://github.com/CITCEuraRFID/KeyDuino), which is a wonderful little board, created by people who said "Fuck NFC shields, lets just build one into an arduino!" This board has been invaluable to me in learning how to make projects using my xNT chip as well as programming it. The antenna that is built into it reads my chip pretty damn well, but its not too ideal for most projects considering you have to basically touch the controller, limiting your enclosure options. It does, however, also have a UFL conenctor on it, for connecting external antennas, which is why I chose to model this design after it.

It's based around the [PN532] (https://cdn-shop.adafruit.com/datasheets/pn532ds.pdf) chip, which handles all of the NFC to serial communication, making it compatible with most development boards and DIY electronics.

##The antenna
As many people that there are with the xNT implant, there is surprisingly little documentation on using it well in DIY projects using microcontrollers. Through the [Biohack.me](http://forum.biohack.me/categories/all) forums, I was able to get in touch with user [Fred](http://forum.biohack.me/profile/15790/Fred), who recommended the [DLP-FANT](http://www.mouser.com/Search/Refine.aspx?Keyword=DLP-FANT). Fred used this antenna in his [NFC computer login](https://0xfred.wordpress.com/2015/11/26/nfc-login-2-0-finally-working/) system, where he scans his tag and has the board type in his password. He found the antenna through the work of [Mathieu Stephan](http://www.limpkin.fr/index.php?post/2014/10/07/Using-a-Standard-Coil-for-NFC-Tag-Implant-Reading), who figured out the best coil type for reading the xNT accurately through his voodoo black magic (This shit goes right over my head, so I am very grateful for his work). 

This is as far as my research has gotten me on the best way to interface with the xNT for DIY projects, and as far as I know, as far as anyone else has either. Trust me, I've looked everywhere.

# Why not make it myself?
The reason I'm putting this project on GitHub is becasue, honestly, I have no idea what I'm doing when it comes to designing a pcb. The schematic included in this repository is the first one Iv'e made, and its mostly just bits and pieces stolen from other open-source projects. I'm looking for people more skilled than I to collaborate and build upon the idea behind this board, because I think it could potentially be a very handy tool for grinders and DIYers alike.

# What you can do to help

## Proof the Schematic
Like I said, this is the first schematic I've made. and even then I barely know whats going on in it. I emailed it to the creator of the Keyduino, and thusly the original circuit itself, and he said it looked good, but the more eyes on it the better. The PN532 chip is capable of communicating via SPI, UART, and I2C, and I havent chosen which one it should use yet. If you know which one would work best, let me know.

## Layout the PCB
The reason I decided not to use the keyduino is the fact that it locks you into using an arduino Leonardo, which isnt inherently bad until you run out of memory. Any decently complicated sketch will fill that puppy up in no time. I decided to switch to the [Teensy 3.5](https://www.pjrc.com/store/teensy35.html) for its extended memory, more IO's, and built in microsd reader. My hope is to make an expansion board that could fit onto the teensy, in order to make compact, flexible, and powerful projects for my xNT transponder. 

However, dont feel like you have to do the same, if you have another layout in mind, go for it, it's all open source so do what you wish.

## Share Ideas
This has the possibility of being a very useful tool for anyone who wants to hack together stuff for their xNT, and only you guys know how to make it more useful. Contribute to its design, make it your own.

# Sidenote
this is the first public GitHub repo that I've made. If you have any pointers, shoot me a message, I'd love to hear them.
