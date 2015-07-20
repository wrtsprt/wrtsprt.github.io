---
layout: post
title: Notification for long(er) running command line processes (on Mac OS X)
categories: []
tags: []
status: publish
type: post
published: true
meta:
  _publicize_pending: '1'
author: wrtsprt
---

It happens several times daily, that I have to fire off a command that will take more than one
minute (bundle install, cap deploy, ...). This is exactly the time I need to start focussing
on other things and forgetting to return often to check on the task. Recently I figured that it
would be great to just get a notification once the command was done(, so I can come back from
reading hacker news to continue my work).</p>

Google gave me this <a title="Notification when commands are done" href="http://apple.stackexchange.com/questions/9412/how-to-get-a-notification-when-my-commands-are-done">stack exchange question</a> 
and in combination with <a title="Notification centre from apple script" href="http://apple.stackexchange.com/questions/57412/how-can-i-trigger-a-notification-center-notification-from-an-applescript-or-shel">this one</a>
(on the use of Notification Center) I settled on the following aliases for my zsh:

{% highlight bash %}
NOTIFICATION='display notification "It is fullfilled."; with title "Done"'
alias -g nd='; osascript -e $NOTIFICATION'
alias -g sd='; say done; nd'
{% endhighlight %}


This gives my two options: I append '<em>sd' </em>to basically any command (sometimes I have to use '<em>; sd') </em>and I will hear the spoken 'done' and see a notification popup. Should I be in a surrounding where the audio channel is not a good choice I can use '<em>nd'</em> and I will just get the Notification Center popup.
