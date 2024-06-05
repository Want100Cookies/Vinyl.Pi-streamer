# Vinyl.Pi-streamer
Setup a Pi to stream vinyl to a Sonos speaker

Use the provision playbook to setup and configure your pi to stream a connected Behringer UFO202 to a sonos speaker.

You can find the webinterface on [vinyl.local:8000](http://vinyl.local:8000/)

I used [this repo](https://github.com/basdp/USB-Turntables-to-Sonos-with-RPi) to base my config on.

You can use home-assistant to start the stream with the following service call:
```yaml
service: media_player.play_media
target:
  entity_id: media_player.dining_room
data:
  media_content_id: x-rincon-mp3radio://http://vinyl.local:8000/turntable.mp3.m3u
  media_content_type: music
  enqueue: replace
```