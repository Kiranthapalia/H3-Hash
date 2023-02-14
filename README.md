# H3-Hash
## x) Read and summarize
- ONE-WAY FUNCTIONS

One way functions are simple to compute but difficult to reverse, which is why they are crucial for public-key cryptography. Even though many functions seem to be one-way, there is no mathematical evidence to support their existence. An example of one way function is:imagine we have some uncooked rice and we cook it see easy to compute but now we cannot revert back the cooked rice to uncooked rice in other word difficult or impossible to reverse. 

Trapdoor one-way functions, which have a hidden trapdoor, can be utilized for encryption whereas regular one-way functions cannot. If you know the secret, it is simple to compute trapdoor one-way functions in the other direction, even though they are difficult to compute in one direction. Its like playing a Game, if you know the cheat or secret code then you can easily. An example of Trapdoor function is: imine we are playing a game in this case the classic GTA Vicecity and you are being chased by the police, either you can run and try to lose them or you can simply use the code 'leavemealone'. So if somebody is new to this game and doesn't know that they can just easily get rid of the police then it's gonne be really difficult for them to complete the mission. 

- ONE-WAY HASH FUNCTIONS

one-way hash function takes an input and generates a fixed-length output that acts as a fingerprint for the input. Although it is simple to calculate the output from the input, it is challenging to determine the input from the output. It is difficult to discover two separate inputs that result in the same output when using a decent one-way hash function, which is also collision-free. The integrity of communications and data is guaranteed, and identities are verified, using one-way hash functions in cryptography. Only a person in possession of the secret key may validate the output of a message authentication code (MAC), which is a one-way hash function. An example of one way hash function is the SHA-256 (Secure Hash Algorithm 256-bit). SHA-256 takes an input message of any length and produces a fixed-length 256-bit output, which serves as a unique digital fingerprint of the input message.

## a) Install Hashcat

Installing stuff in linux is really convenient. First i used the command `sudo apt-get update` followed by `sudo apt-get -y install hashid hashcat wget` 
then I just had to make a directory name hashed `mkdir hashed` and change the directory to hashed using the command `cd hashed`. 

<img width="578" alt="hash install" src="https://user-images.githubusercontent.com/102954934/218867919-b718c838-df13-476b-bc3a-e015dd1ca7a1.png">

## b) Crack this hash 8eb8e307a6d649bc7fb51443a06a216f

This was a fail for me as i tried almost everything to make it work but couldn't.

<img width="572" alt="hash1" src="https://user-images.githubusercontent.com/102954934/218869295-017c1f9d-067d-4cf8-8471-2ab5e1a02c36.png">

<img width="602" alt="hash2" src="https://user-images.githubusercontent.com/102954934/218869359-0003480a-f424-4381-8d42-2cbb037607f3.png">

<img width="602" alt="hash3" src="https://user-images.githubusercontent.com/102954934/218869390-59abd185-1610-4281-a0aa-844e79e35f45.png">

As seen in the image above we can see it said initializing backend runtime for device #1...illegal instruction, so i tried to find out how to fix it , I read somewhere that the fix was downloading OpenCL but it didnt work or maybe i dont know how to make it work. So Tero has agreed to help me with this in the next class.

## c) Compile John the Ripper, Jumbo version

I followed the [instruction](https://terokarvinen.com/2023/crack-file-password-with-john/) Before installing and compiling we had to install some prerequisites. I used the command `sudo apt-get -y install micro bash-completion git build-essential libssl-dev zlib1g zlib1g-dev zlib-gst libbz2-1.0 libbz2-dev atool zip wget`. then had to clone the whole project using the ommand `git clone --depth=1 https://github.com/openwall/john.git`.

After that i changed to another directory `cd john/src/	` followed by `./configure` to detect the environment and create a Makefile for 'make' command. 

<img width="581" alt="completed successfully" src="https://user-images.githubusercontent.com/102954934/218871602-8c07e53d-a4a9-4667-9d12-482b735f99ff.png">

## d) Crack a zip file password

Again i followed the [instruction](https://terokarvinen.com/2023/crack-file-password-with-john/). First i got the zip file `wget https://TeroKarvinen.com/2023/crack-file-password-with-john/tero.zip` and then I started the cracking process whcih consisted of 2 step.

The first was extract the hash into a new file (In thsi case tero.zip.hash.) then the 2nd step was letting john perform dictionary attack using the command `$HOME/john/run/john tero.zip.hash`.


<img width="578" alt="password (zip file)" src="https://user-images.githubusercontent.com/102954934/218875664-75f38a3c-9cf5-48d3-a448-60b0518814fb.png">

In the image above the main part is highlighted in orange colour --> butterfly        (tero.zip/secretFiles/SECRET.md)  
Now we just unzip the file using the command `unzip tero.zip `. `cat secretFiles/SECRET.md ` and walla!

<img width="581" alt="completed successfully" src="https://user-images.githubusercontent.com/102954934/218876180-07f27898-da7c-49a6-af06-c17fa156539e.png">
