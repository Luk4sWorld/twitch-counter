# twitch-counter
a little text page that counts up with each command executed

### Usage:

1. add browser source to OBS, use the full URL `https://luk4sworld.github.io/twitch-counter/index.html`
2. add the arguments to customize the coutner after a `#` character in the hash value of the URL, encode it like URI parameters
   * channel: mandatory! your channelname/id
   * value: optional! the starting value of your counter, default: `0`
   * command: optional! the command that increases the counter, default: `!count`
   * text: optional! the text around the counter value, default: `Counter: {value}`
   * perm: optional! the permission level needed to increase the counter, default: `1`
   * cooldown: optional! the time in milliseconds until next command is accepted, default: `2000` ms
3. refresh your browser source to reset counter

#### Permission values

*  0: Broadcaster  
*  1: Moderator  
*  2: VIP  
*  3: Subscriber  
*  4: everyone  
  
#### Example

URL: `https://luk4sworld.github.io/twitch-counter/index.html#channel=luk4sworld&command=!death&perm=4&text=Lukas%20died%20%7Bvalue%7D%20times.`

this evaluates to:  
```json
{
  "channel": "luk4sworld",
  "command": "!death",
  "value": 0,
  "perm": 4,
  "text": "Lukas died {value} times.",
  "cooldown": 2000
}
```

and with a counter value of 3, this will display  
![example image](/img/example.jpg)  


### Style Customisation

Can be changed via OBS "Custom CSS" inside the Browser Source properties.  
The DOM has the `message` class:  

```css
.message {
    color: #F0F0F0;
    font-family: Comic Sans MS, sans-serif;
    font-size: 40px;
    text-align: center;
}
```
