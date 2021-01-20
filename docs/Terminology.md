# Terminology
This lists all the terms that are used in this documentation. These terms are also used in the bot. Please refer this page whenever you do not understand any term.
## Chat
A chat in telegram can be a user, bot, group, or channel. It means that anywhere that you can send or receive a message is a chat.

 ### Example:
When you send */start* to @auto_forwarder_bot, you start a chat with that bot.
### Source Chat
A source chat is any [chat](#chat) from where you want to copy messages. This is usually the [chat](#chat) where you are not an admin.

**Incoming chat** is also used in place of source chat.

 ### Example: 
Let us say that you want to copy messages from a channel A to channel B. All the messages which are sent to channel A will be sent to channel B by the bot.

Here, channel A is the source chat.
### Destination Chat
A destination chat is any [chat](#chat) to where you want to copy messages. This is the [chat](#chat) where you are an admin.

**Outgoing chat** and **target chat** are also used in place of destination chat.

 ### Example: 
Let us say that you want to copy messages from a channel A to channel B. All the messages which are sent to channel A will be sent to channel B by the bot.

Here, channel B is the source chat.

Please not that you MUST have message sending privilege in the destination chat.
You should be an admin with the permission to send messages if the destination chat is a channel.
## Filter

Filter refers to the complete system of [blacklist](#blacklist), [whitelist](#whitelist) and [text replacement].

Filter will usually be used in place of [text replacement].
### Text Replacement
Text replacement refers to the replacing of some part of text of a message with another text.

 ### Example: 
Say the [source chat](#source-chat) A receives the following message:
```
Stop Loss 2.32
Take Profit 1.32
@sourcechannel
```

You can apply text replacement to convert this text to 
```
SL 2.32
TP 1.32
@destinationchannel
```

The replacement applied here is:
`Stop Loss` -> `SL`
`Take Profile` -> `TP`
`@sourcechannel` -> `@destinationchannel`

 ### Special Features:
You can even replace emojis!

 #### Note
Sometimes simply "Filter" will be used in place of Text Replacement. 
### Whitelist
Whitelist is a list of words which will set the bot to copy messages ONLY when AT LEAST ONE of those words in the whitelist are present in the message.

 ### Example:
**Whitelist**: `SL, TP`

In this configuration, any message that does not contain either of SL or TP will not be sent to [destination chat](#destination-chat).

1. `Please follow my instagram account @instagram`
2. `SL 2.02`
    `TP 2.023`
    `Good luck`
3. `SL 2.3`

Messages 2 and 3 will be sent but 1 will not be sent to destination chat.
### Blacklist
Blacklist is a list of words which will set the bot to NOT copy messages when ANY ONE of those words in the blacklist are present in the message.

 ### Example:
**Blacklist**: `instagram, facebook`

In this configuration, any message that does not contain either of instagram or facebook will be sent to [destination chat](#destination-chat).

1. `Please follow my instagram account @instagram`
2. `SL 2.02`
    `TP 2.023`
    `Good luck`
3. `SL 2.3`

Messages 2 and 3 will be sent but 1 will not be sent to destination chat because 1 contains `instagram` which is present in our blacklist.

 ### Important
**Only one** of blacklist or whitelist will work. Whitelist will be given priority over blacklist if both are set.
## Delay
Delay means how late a message is sent after it is received in the [source chat](#source-chat).

All the messages are sent instantaneously by default, meaning no delay. But delay can be added to all the messages for any reason. It is usually in seconds.

 ### Example:
If delay is set to 5 seconds, all the messages received in the source chat will be sent after 5 seconds to the destination chat.
## Others
 ## Incoming chat
Same as [Source Chat](#source-chat)

 ## Outgoing chat
Same as [Destination Chat](#destination-chat)

 ## Target chat
Same as [Destination Chat](#destination-chat)
