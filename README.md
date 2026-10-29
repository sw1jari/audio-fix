# audio-fix

Fixes pitched down or slowed audio on PipeWire after apps fight over the sample rate.

It turns the default sound card's profile off and back on, which makes PipeWire reopen the device and renegotiate the clock. Afterwards it sets the sink as default again and moves every playing stream back onto it.

If one Firefox tab still sounds off afterwards, reload that tab.

## Requirements
PipeWire with `pactl` (pipewire-pulse), dmenu for `pick`.

Notifications use `dunstify` if installed, otherwise `notify-send`. Without either, it still works but stays silent.

## Install
```sh
cp audio-fix ~/.local/bin/
```

## Usage
Reset the card behind the default sink:
```sh
audio-fix
```

Choose the card from a dmenu list instead:
```sh
audio-fix pick
```
