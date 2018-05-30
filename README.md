# Slack interactive message in Golang

This is sample slack bot which uses [slack interactive message](https://api.slack.com/interactive-messages) written in Golang. To run this bot, you need to create a bot as [slack app](https://api.slack.com/slack-apps). To create slack app only for your team, you can use [internal integrations](https://api.slack.com/internal-integrations) (No OAuth required. This code does not implement it, so if you want to distribute it, you need to write it by yourself). Create a new app from [here](https://api.slack.com/apps). The following is how this bot works. Feel free to fork this repository and write your own! Cheers :beer:

![](/beerbot.gif)

(NOTE: Order is fake...)

## Usage

To run this bot, you need to set the following env vars,

```bash
export BOT_ID="U***"             // you can get this after create a bot user (via slack app management console)
export BOT_TOKEN="xoxb-***"      // you can get this after create a bot user (via slack app management console)
export VERIFICATION_TOKEN="***"  // you can get this after enable interactive message (via slack app management console)
export CHANNEL_ID="C***"         // bot reacts only this channel
```

To run this,

```bash
$ dep ensure
$ go build -o bot && ./bot
```

To run this local, use `ngrok` (See more about it [here](https://api.slack.com/tutorials/tunneling-with-ngrok)) and set it for interactive message requests endpoint.

## References

- https://github.com/slackapi/sample-message-menus-node


## ToDo
- makefile that has a container build see : https://github.com/manifoldco/deployhelper/blob/master/makefile as References
- ship container to hub
- test on hyper
- change drop down to be choosing what product to make an issue for
- pull in code from shipit
- test creating of github issue via slack bot

## Future works
- have it make the tags in GH after user just type in the version number
- something like : make release issue for v1.0.0
  - triggers making release issue AND tag -rc.0
- add a "new tag command": what product -> release or rc -> give number
