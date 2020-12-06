# notes-on-crypto-stuff

This is be where i will take down notes of everything i learn about cryptocurrency so far. This is a personal page, You can read it but keep in mind that this is what I understood from what i learn.. and I'm pretty dumb.

# Bitcoin Transaction
Guy creates a dropbox thing also known as an address. It is disposable and he has the key, he sends the address to the guy that's gonna send him the btc and that's how a transaction works. This is my first note, if it's somehow false, I'll update it.. Or not

# Money
Commodity: items have value. examples: bear pelt, beaver pelt, wool, rawr materials, etc.
Representative: stuff like gold certificates, paper, etc are considered valueable.
Fiat: the government declares what has value, i.e, money - euro, yen, rupee, etc.

# Bitcoin transaction thing again
when you send someone bitcoin, the network needs to verify that it's real. They need confirmation. This is good because let's say that you are a user with 11 bitcoin. That's a lotta bitcoin. You have your address right? Yes. You also have a private key for spending your bitcoin. let's say that someone pretends to be you with YOUR address. If there's no actual confirmation, people are gonnna be spending your bitcoin left and right. Hence, confirmation is good. This is what i learned so far.

# Hashes and Fingerprinting
Why am i now writing about hashes? Well it is an important factor especially in bitcoin. So imagine this. You are writing a letter to your friend and u don't want anyone else to understand it except for your friend ONLY. This means that u need some sort of secret message to send to them. Have you ever seen those little ciphers that people use for example. a=b b=c c=d. This is the most basic form of cryptography. Though this is not good for security because.. anyone can find your cipher or they can decode it themselves because it follows a pattern. Now let's suppose that you are in a wedding and someone cut the cake too early (there's only 4 people in your wedding because you're lonely). There's a fingerprint on the knife and u want to find out who cut the cake so u test out everyone's fingerprints in the wedding and try and see which one matches the fingerprint on the knife. This is an example of a one-way hash. You can't make out WHAT the person looks like with just their fingerprint, u need to verify it. Why is this important? well it's commonly used in sha256, we'll get into that.

# sha256
Now i don't know exactly how sha256 works but i know how to use it. Now let's say that you have a website, and this website has a login page, u need to somehow store the passwords safely. Now u might be thinking "why not just store it in a database"? well you're partly right BUT what if someone breaks into the website somehow? they can just steal the passwords and emails and try it on every site with the same credentials (most people don't use different passwords for each site) To solve this we use sha256. Now sha256 is a hashing algorithm it's a one way algorithm meaning u cant decode something with the output of encoding something. ANYWAY what u do is you hash the password of each user and compare it to the database of hashes that you have. What do i mean by this? well let's say for example u have a user in your site named Molly. Molly's favourite password is "abc" and when u hash "abc" with the the sha256 algorithm you get edeaaff3f1774ad2888673770c6d64097e391bc362d7d6fb34982ddf0efd18cb. Now why is this important? well let's say that molly's second favourite password is Abc (capital A). The hash output of Abc is 74d1a9df6306221a06599489653ab29e78c3a96efe61851c61cae0cd6d6c2579. See how different that looks comparing abc with Abc? well u just check the hash outputs of the passwords and u have pretty basic security. We'll get on to why this is important in bitcoin later.

# Verifying the integrity of a file with sha256
Now, Suppose that u have paid for a file (for this case we're just gonna use a .iso file.). Now u want to make sure that the file is not fake, the site has given you a hash output of the file. For this we're going to use the official kali linux 2020.4 live iso. Now we're going to use a terminal to find out if the file is real so if you're not familiar with a terminal, that's ok too. Kali linux has given us a sha256 output file and the hash is - 4d764a2ba67f41495c17247184d24b7f9ac9a7c57415bbbed663402aec78952b. Now we are going to hash the .iso file and the command is - openssl dgst -sha256 <file> . Now we're going to test this out on the actual iso and see if we get the same results. AAAAAAND we get the same exact result! - 4d764a2ba67f41495c17247184d24b7f9ac9a7c57415bbbed663402aec78952b If someone was to give u a fake file, you would know bc one small change to the file can completely change the hash. This was demonstrated in the last topic.
