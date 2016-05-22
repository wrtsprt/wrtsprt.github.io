---
title: Playing with Alfred 3 list filters 
date: 2016-05-22 19:52:00
layout: post
categories: []
tags: []
---

[Alfred 3](https://www.alfredapp.com) is out and I was very curious to spend some time with it. I had 30 minutes today and so I had a quick look at what's possible with workflows in the new version. So far I didn't find any articles specifically on Alfred 3 workflows so I just started by playing around with it and checking what the UI can tell me about how this works. 

I went to a very simple workflow that a colleague of mine created to turn our VPN on and off. As simple as it could be. Two keyword filters: 'vpn on', 'vpn off' connected to each one 'run script' action calling the appropriate Apple Script to tell Tunneblick to connect or disconnect. There must be room for improvement there, with all the new Alfred 3 features. 

![Intermediate Workflow]({{ site.url }}/assets/2016/alfred-vpn-initial.png)

I started by opening the workflow part of Alfred. Opened Alfred Preferences (for me that is ⌘+space and ⌘+,) and clicked on Workflows. 
Clicking through the options (right click on the workflow canvas) I came across the 'Script filter' that sounded interesting. I had a vague idea what that was from looking at the included example workflow 'Simple To-Do List'. 

For my workflow I have one input keyword 'vpn' and then a fixed list of two options. 'on', 'off'. Sounds like a list. Let's see where we get.

So I replaced the two script filters with one list filter defining the 'on' and 'off' list item. (Bottom right I configured Alfred to keep the list order, since I might end up using the arrow keys to select the option and I don't want that changing three times per day).

![List Filter Configuration]({{ site.url }}/assets/2016/alfred-list-filter-on-off.png)
 
OK to make it work we still need a 'Utilities -> Filter' to distinguish the 'on' and 'off' case, for now. 

![Alfred 3 Filter]({{ site.url }}/assets/2016/alfred-utilities-filter.png)

So that leaves us with that configuration. (Description on nodes done with right click -> 'edit note').

![Intermediate Workflow]({{ site.url }}/assets/2016/alfred-vpn-two-filters.png)

But the of course, of the only difference in the Apple Scripts is the name of the command, why not using the list filter argument field to pass the exact command. This will make our workflow look a lot simpler and us feel good about ourselves. So configure list item 'on' to pass 'connect' and 'off' to pass 'disconnect'.

![Update arg in list item]({{ site.url }}/assets/2016/alfred-vpn-arg-connect.png)

Change the Apple Script to use '{query}' instead of the hard coded command ... 

![New Apple Script]({{ site.url }}/assets/2016/alfred-vpn-dyn-script.png)

... and: we're done. 

![New Apple Script]({{ site.url }}/assets/2016/alfred-vpn-final.png)

After spending a tiny bit of time with it, I see a great future for Alfred 3 (in my life). It's a lot of fun to play with and there are soo many possibilities. The list filter is a great feature to introduce, since it makes the basic case of different options for a command simple and doesn't necessitate any scripting to get that part done. 

P.S. Small remark: I like to see the options for a command one I have selected it, in case I don't use it often and forget the exact wording. Apparently turning the 'with space' checkbox off, gives you the list of options once you hit 'tab' or complete the command name. Otherwise you need to type the first letter to show matching options. 

![Simple Alfred 2 Workflow]({{ site.url }}/assets/2016/alfred-vpn-with-space.png)



