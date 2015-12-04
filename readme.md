Add following line to ion-content in index.html
'''
<div class=”videoContainer”>
<iframe src=https://www.youtube.com/embed/wyVM1evRxNw frameborder="0></iframe>
</div>
'''

Embeding a youtube video is quite easy but when whitelist plugin is used, it will block  the youtube api’s . so add following lines to config.xml

'''
<access origin="*.youtube.com"/>
<access origin="*.ytimg.com"/>
'''

These lines whitelist the youtube api’s and will allow the youtube video to be played in ionic app.

Setting the Aspect Ration:

The default aspect ration of youtube video is 16:9 so just create a wrapper <div> with a percentage value for padding-bottom, like this:

div {
width: 100%;
padding-bottom: 56.25%;
}


It will result in a <div> with height equal to 56.25% of the width of its container (a 16:9 aspect ratio).
Padding-bottom values for other aspect ratios and 100% width :
aspect ratio  | padding-bottom value
--------------|----------------------
16:9      |       56.25%
4:3       |       75%
3:2       |       66.66%
8:5       |       62.5%

Disabling relative links and branding or title

One of the most common issue while embedding youtube video is relative links and branding and title, so add following query string to the embed url

Actual url :

https://www.youtube.com/embed/wyVM1evRxNw

Url without relative link and branding

https://www.youtube.com/embed/wyVM1evRxNw?rel=0&&modestbranding=1

title can be disabled or removed using showinfo=0;

But either title or branding, anyone of them can be disabled. If both title and branding are not disabled and user click on them, youtube player will take over the app and there is no way back to app other than killing the app and start it again.

So disable the branding and handle the title by adding transparent div or container on the title which makes it disable otherwise like

<div class="videoTitleDisable”></div>
<div class=" videoContainer">
	<iframe src="https://www.youtube.com/embed/wyVM1evRxNw"></iframe>
</div>

CSS:
.videoTitleDisable{
width: 100%;
height: 50px;
background:  transparent;
z-index: 1000;
position: absolute;	top: 0px
}
