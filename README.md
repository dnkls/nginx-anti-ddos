# nginx-anti-ddos
This is my standard configuration I use to reduce the effectiveness of layer 7 ddos attacks.

## What this alone can do?
This script alone can block small layer7 denial of service attacks. Once attacks get larger you'll have to take other measures to block the evil sources from connecting to your server.

## So what about botnets? What do I do?
Well nginx can only process so many requests per second due to the limits of a single server. That being said there are a few things you can do. First if you are being attacked with frequent, large attacks, get the most powerful server you can afford (make sure it has powerful and multiple CPUs), second you should configure fail2ban to ban repeat infringers of your rate limits. I personally use fail2ban to issue Cloudflare IP Address Bans with their API. A botnet unfortently due to the size will hit of your site at first but within 5-15 minutes of the attack starting fail2ban SHOULD finish banning all of the evil IPs and your site will be back. At the moment I haven't published my fail2ban configs. I may do so later.
