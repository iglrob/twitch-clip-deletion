# Introduction

Delete all clips of your twitch.tv account.
Not the ones you created, but all clips taken for your stream.

# Disclaimer

This uses not officially documented APIs from twitch.
Use at your own risk.

# How to get it to work

To get this to work you have to use a beautful tool called [Postman](https://www.postman.com/) <br>
(don't worry, no signup necessary and it's free to use)

After you installed this we can get started: 

1. Import the [postman collection from this repo](postman.json). For ease of use you can just use the url: `https://github.com/iglrob/twitch-clip-deletion/blob/master/postman.json`
2. Create a new environment for postman
3. Add the following variables to the environment
    * *slugs* with *initial value* set to *[]*
    * *auth* with *intial value* set to your obtained twitch variable
    * *clientId* with *initial value* set to your obtained twitch variable
    * *username* with *initial value* set to your twitch channel's name
    * *broadcasterId* with *initial value* set to your obtained twitch variable
4. Open up the test runner
5. select your created environment
6. hit run

This should fetch 20 clips, delete those and start over again and again until no more clips where found.

## How to get your twitch account details

The variable *username* is skipped a this is just the name of your channel and you should know that ;)

Hint: you need to be logged in for the following steps

### Chrome

1. Open up https://dashboard.twitch.tv/ in the browser
2. Go to the options panel, select *More Tools* and from the dropdown *Developer tools* (on windows you can also just hit F12, on Mac CMD+Alt+I)
3. In the developer tools opened at the bottom, select the *Network* tab
4. In the network tab, select the *XHR* option (if anything is shown there, hit the *Clear* button, making the following steps easier)
5. On the left in your browser, select the *Content* dropdown and open *Clips*
6. You should see multiple listings in your developer tools at the bottom, select the *gql* request
7. If not allready selected, select the *Headers* tab
8. Scroll down (and if you like close all other groupings) until you find *Request Headers*
9. Your *auth* variable is the value in the *Authorization* field (without the *OAuth*)
10. Your *clientId* variable is the value in the *Client-Id* field
11. For your *broadcasterId* variable it gets more complicated, scroll down a bit more in the developer tools until you see *Request Payload*
12. Click *view source* right next to it
13. You should find a field *curatorID* (if on the website the first options is selected) or *broadcasterId* (if the second option is selected)
14. Regardless of what is selected, use that value as your broadcasterId

