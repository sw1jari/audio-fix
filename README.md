# audio-fix

Fixes pitched down or slowed audio on PipeWire after apps fight over the sample rate.

It turns the default sound card's profile off and back on, which makes PipeWire reopen the device and renegotiate the clock. Afterwards it sets the sink as default again and moves every playing stream back onto it.

If one Firefox tab still sounds off afterwards, reload that tab.

## Requirements
PipeWire with `pactl` (pipewire-pulse), dunst (`dunstify`) for notifications, dmenu for `pick`

## Install
```sh
cp audio-fix ~/.local/bin/
```

## Usage
```sh
audio-fix        # reset the card behind the default sink
audio-fix pick   # choose the card from a dmenu list
```
