# Sleepy Discord
C++ library for Discord

# [Documenation](https://nonamer64.github.io/sleepy-discord/documentation.html)
The docs are here https://nonamer64.github.io/sleepy-discord/documentation.html . If you like to edit them, please check out the docs branch.

# Why?
Just for the novelty of using a C++ library for Discord. I would also love for this thing to work on many things like consoles and maybe some microcontrollers.

# Example
```cpp
#include <sleepy_discord>

class myClientClass : public SleepyDiscord::DiscordClient {
public:
    using DiscordClient::DiscordClient;
    void onMessage(std::string * jsonMessage) {
   	    SleepyDiscord::Message message(jsonMessage);
	    if (message.content.find("whcg hello") == 0)
	        sendMessage(message.channel_id, "Hello " + message.author.username);
    }
};

int main() {
    myClientClass client("token");
    while(true)
        std::this_thread::sleep_for(std::chrono::seconds(1));
}
```
Input: Message received
```
whcg hello
```
Possible Output: Message sent
```
Hello Sleepy Flower Girl
```
# Will Updating the library break my bot?

Yes, and for now I don't plan on making 0.0 versions backwards compatable with 1.0 versions or later.

# Requirements
* [OpenSSL](https://www.openssl.org/)
* [cpr](https://github.com/whoshuu/cpr)
* [Websocket++](https://github.com/zaphoyd/websocketpp)
or
[uWebSockets](https://github.com/uWebSockets/uWebSockets)

# Develop Breach
For the cutting edge of Sleepy Discord, check out the develop breach. Please use the develop breach with caution because it may not even be able to complie or it is 100% not tested at all. Other then that, the breach is used for code that may not work.
