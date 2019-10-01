
## Fork of iphelix's dnschef with telegram support (and some tweaks)

### Telegram bot support
You will need a registered telegram bot added to a private channel.
You can get a channel's ID number in web version of telegram when you click on it, example:
https://web.telegram.org/#/im?p=c11111111_4745745776645745745785
Here you need to get the number between "c" and "_", this is your channel ID number.
After this you need to make some filter string line because telegram doesn't like spam. So good example is something no one will ask your NS server for (like some random string)

Example of usage:

```dnschef -i 0.0.0.0 --telegram="your bot token" --telegramChannel="your channel ID" --telegramString="c90ke1"```

You can test this with digging c90ke1.yourdomain.com, the message should drop to your private channel.
Every client's IP in the telegram message is an inline link to ipinfo.io.

### Other tweaks
Flags --trueip and --trueipv6 added.
So in case you want to use dnschef as a NS server for your domain, but doesn't want to resolve all the shit some bots in the internets want you to, you can do something like this:

```dnschef -i 0.0.0.0 --fakeip=127.0.0.2 --truedomains=*.mydomain.com --trueip=101.101.101.101```

After this dnschef will resolve all mydomain.com subdomains to 101.101.101.101 and all the other ones to 127.0.0.2
