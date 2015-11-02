# Pidash

A personal desktop dashboard, showing Github contributions and a clock, running on a Raspberry Pi and an Adafruit PiTFT display.

Pidash is written in NodeJS, and uses RxJS to manage asynchronous event streams.

## Installation

1. Setup your PiTFT
  1. Install [Adafruit's PiTFT helper](https://github.com/adafruit/Adafruit-PiTFT-Helper):
```
curl -SLs https://apt.adafruit.com/add | sudo bash
sudo apt-get install raspberrypi-bootloader
sudo apt-get install adafruit-pitft-helper
```

  2. Configure the PiTFT:
```
sudo adafruit-pitft-helper -t 28r
```
_The argument you use here may be different, depending on which TFT you have; run `adafruit-pitft-helper -h` for a list of options_

2. Setup NodeJS to run on boot
  1. Add NodeSource's repo:
```
curl -sL https://deb.nodesource.com/setup_4.x | sudo bash -
```
  2. Install NodeJS:
```
sudo apt-get install -y nodejs
```

  3. Install [PM2](http://pm2.keymetrics.io/)
```
sudo npm install -g pm2
```

  4. Configure PM2 to run as a service on startup
```
sudo pm2 startup -u pi
```

3. Install Pidash
  1. Install Cairo, a dependency of the node-pitft library:
```
sudo apt-get install libcairo2-dev
```
  2. Clone the Pidash repo into the `pi` user's `pidash` directory
```
git clone https://github.com/jstrutz/pidash ~/pidash
```

  3. Install Pidash's NPM dependencies:
```
cd ~/pidash
npm i
```