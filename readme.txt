APRS to Twitter gateway

A few years ago http://www.hamradiotweets.com/ was born.
They eventually went offline, never said what happened or why they went down.

So I started it back up, the system works the same way theirs did.
Their setup however is closed-source as far as I can tell. Mine however is not.

Do what you will with it just be curtious and use your legal callsign.

You will find the following code in the script. Please update it with your own information.
To create your personal twitter credentials go to https://apps.twitter.com/ and log in with 
the twitter account you want to use.  
Choose "Create New App" and follow the directions to generate your application keys and access tokens.

  $client = Twitter::REST::Client.new do |config|
  config.consumer_key        = "your_key_here"
  config.consumer_secret     = "your_key_here"
  config.access_token        = "your_key_here"
  config.access_token_secret = "your_key_here"
end

  
  aprs = Aprs.new("second.aprs.net", 20157, "your_callsign_here")
  aprs.connect
  aprs.packet("=4158.19N/08556.81W$", "Twitter Gateway YOUR MSG HERE")


As a final note if I can keep it running, feel free to take a look at my setup.

https://twitter.com/APRS_GW
