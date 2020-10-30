# RollJam

This is a Github repository devoted to delivering to you
the necessary and required tools and hardware to perform [Samy Kamkar](https://github.com/samyk)'s RollJam attack.

*This is for educational purposes only.
I am in NO WAY liable for any actions executed by means of the contents within this
repository. PLEASE use responsibly.*

## Prerequisites:

### Hardware:
• Raspberry Pi (3B+ reccomended)

• YARD Stick One (With ANT500 Telescopic antenna, reccomended)

• SDR Dongle (Only necessary for finding the frequency of target; Without it, you can do a plate lookup and find the fob frequency online)
### Software:

• Install [Raspbian](https://www.raspberrypi.org/downloads/raspbian/) on your Raspberry Pi

• Install [Rpitx](https://github.com/F5OEO/rpitx) on your Raspberry Pi

• Install [RfCat](https://github.com/atlas0fd00m/rfcat) on your machine (it should be a portable laptop)

## Getting started:

Make sure you have a wire attatched to the GPIO pin of your Raspberry Pi to act as an antenna.

"cd" into your Rpitx folder and run:
```
sudo ./sendiq -i /dev/stdin -s 96000 -f <frequency> -t float
```
Set your frequency to be slightly higher or lower than the target frequency.

Run replay.py (Credit to [AndrewMohawk](https://github.com/AndrewMohawk) and their [RfCatHelpers](https://github.com/AndrewMohawk/RfCatHelpers) repository) to listen for the unexpired key:
```
python replay.py -f <frequency> -n <number of keys to collect>
```
Once the key(s) are captured, you may stop jamming.

You now have an unexpired key to use on the target!
