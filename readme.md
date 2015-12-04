# Embedding Video in Ionic App and Issues
###This will help to embed youtube video in ionic app using whitelist plugin and help to resolve the issues while embedding video in app.

Create a blank ionic project using

* # ionic start IonicProject blank *

and add following line to ion-content in index.html

```
<div class=”videoContainer”>
	<iframe src="https://www.youtube.com/embed/wyVM1evRxNw frameborder="0></iframe>
</div>
```

Embeding a youtube video is quite easy but when whitelist plugin is used, it will block  the youtube api’s . so add following lines to config.xml

```
<access origin="*.youtube.com"/>
<access origin="*.ytimg.com"/>
```

These lines whitelist the youtube api’s and will allow the youtube video to be played in ionic app.

Setting the Aspect Ration:

The default aspect ration of youtube video is 16:9 so just create a wrapper <div> with a percentage value for padding-bottom, like this:

```
div {
		width: 100%;
		padding-bottom: 56.25%;
	}
```

It will result in a <div> with height equal to 56.25% of the width of its container (a 16:9 aspect ratio).
Padding-bottom values for other aspect ratios and 100% width :

```
aspect ratio  | padding-bottom value
--------------|----------------------
16:9      |       56.25%
4:3       |       75%
3:2       |       66.66%
8:5       |       62.5%
```

