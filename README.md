# RCETest
Interview project for potential Reuters Creative Engineers

The goal of this project is to build a small, working prototype of Reuters TV. The Reuters TV API works by providing a URL to a video stream, as well as an array comprised of items you'll find inside the stream. Its up to you to decide how to use the data from the API to create a working prototype. Feel free to use whatever tools, libraries, or frameworks you feel comfortable with to build the prototype – or even just go vanilla CSS & JS!

At minimum, your prototype should:

1. GET data from the Reuters TV API.
2. Find and utilize the HLS stream in the response. (Browsers other than Safari require using the [HLS.js](https://github.com/video-dev/hls.js/) library to play the video stream).
3. Create a UI element that informs the user what the current segment is (synced with the video).
4. Create a playlist UI element that displays the *stories* inside the playlist, and allows the user to click them to skip to the beginning of that story.
5. Give your player a nice visual look. You can either borrow from the current Reuters TV design or make your own!


Extra Credit:

1. Disable the standard video controls and create your own play, pause, volume, and scrubber bar.
2. Disable user interaction of playlist / scrubber bar when the user is within an AD playlist item.

## Reuters TV API

`https://mole.prod.reuters.tv/rest/v2/website/content/reutersnow/region/US/country/USA/duration/10`

This API will return an up to date 10 minute program. The most important things you should be concerned with is the HLS stream which is located under `entity.stream.uri` and the items array which is located under `entity.items`.


### Playlist items
A playlist item has many different properties which describe it. The ones you should be concerned with are:

`type`: This tells you the type of item it is. Use this to tell if the item is an actual story, or another part of the program such as openers, teasers, transitions, or ads. Types include `OPENER`,`STORY`,`TEASER`, `MAINTITLE`, `STORY2STORY`, `AD`, `CLOSER`.

`title`: The title of the segment.

`displayCategory`: The section of the item (World, Politics, etc.)

`resources`: This contains several useful associated things such as SEO friendly URLs and images. 

`duration`: The duration of the segment.

`startTime`: The time in the whole program that this segment starts.

If you find yourself getting stuck on anything, don't hesitate to reach out and ask questions. Good luck!