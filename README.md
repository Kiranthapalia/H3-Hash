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

## Crack this hash 8eb8e307a6d649bc7fb51443a06a216f

This was a fail for me as i tried almost everything to make it work. 

<img width="572" alt="hash1" src="https://user-images.githubusercontent.com/102954934/218869295-017c1f9d-067d-4cf8-8471-2ab5e1a02c36.png">

<img width="602" alt="hash2" src="https://user-images.githubusercontent.com/102954934/218869359-0003480a-f424-4381-8d42-2cbb037607f3.png">

<img width="602" alt="hash3" src="https://user-images.githubusercontent.com/102954934/218869390-59abd185-1610-4281-a0aa-844e79e35f45.png">

As seen in the image above we can see it said initializing backend runtime for device #1...illegal instruction, so i tried to find out how to fix it , I read somewhere that the fix was downloading OpenCL but it didnt work or maybe i dont know how to make it work. So Tero has agreed to help me with this in the next class.

## Compile John the Ripper, Jumbo version


