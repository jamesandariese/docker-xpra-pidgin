# Pidgin with Xpra in Docker

## ABSTRACT

Persistent, shared IM.  It's the dream.

With Hangouts, you can have it.  Same with Slack.  Same with HipChat.

Ever try to use [`XEP-0280`](http://xmpp.org/extensions/xep-0280.html)
(XMPP Message Carbons)?

Yeah.

Now you can have persistent, shared IM with Jabber, too.  Hooray!

## USAGE


Run it in docker somewhere:

    vps:~$ vim $HOME/xpra-password
    vps:~$ docker run -p 10000:10000 -v $HOME/xpra-password:/password -v $HOME/purple:/purple jamesandariese/xpra-pidgin

Now attach from somewhere else:

    laptop:~$ vim $HOME/xpra-password
    laptop:~$ xpra attach tcp:SERVERHOSTNAME:10000 --password-file=$HOME/xpra-password --encryption=AES --sharing

Bonus!  Now attach from ANOTHER somewhere else:

    rpi-on-your-tv:~$ vim $HOME/xpra-password
    rpi-on-your-tv:~$ xpra attach tcp:SERVERHOSTNAME:10000 --password-file=$HOME/xpra-password --encryption=AES --sharing

They're all in sync!  Wow!

You can even write part of a message and finish it on another host.

You can reboot them all (except your server) and keep your IMs exactly how you had them.

