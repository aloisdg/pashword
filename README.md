<div align="center">

# Pashword 🔒
**FOSS Hashed Password Generator**\
Passwords done right

<img src="/public/og-image.png">

### The WHAT 😳
Pashword is a hashed password generator that does away with the need to remember passwords. Pashword generates a unique strong password for every single one of your accounts but these passwords aren't just random like the rest of the 91244 other password generators. They are personalized and constant.

### The HOW 🤔
In a nutshell, Pashword is more of a password calculator than a generator. It's kinda like doing the following: `Website + Username + Secret Key = Unique Password`. Since username and secret key are unique, Pashword is able to generate a strong password made just for you and nobody else can generate it because they'll never know the details you put in it.

Not only does this mean that you won't ever forget how to generate the pashword, but since Pashword generates a password based on the details you put in, your password will remain constant. You can always generate it back when you forget it and you don't even need to remember it! All of this while not storing any data, not connecting to an external server or service. All of this takes place on your device, safe and secure using world-class one-way encryption algorithms.

# 🔒 https://pashword.app 🔒
</div>

# Benefits 🚀
✔ Works offline\
✔ No data stored\
✔ Impossible to crack\
✔ Cryptographically secure\
✔ Never forget your passwords\
✔ Generate passwords on the go\
✔ Same password for same input\
✔ A single key to generate unique passwords\
✔ Progressive Web App, install on any device\
✔ Unique strong passsword for every account\
✔ Can only be generated by the key owner, nobody else

[Pashword.app has verifiable deployments. This means that what you see here is the exact same code that's being used on pashword.app, nothing added, nothing ripped.](https://github.com/pashword/pashword/deployments/activity_log?environment=Production)

Desktop and Mobile apps coming soon!

# Algorithm 👨‍💻
The Pashword algorithm has been extensively documented with comments. You can read the [pashword.ts](https://github.com/pashword/pashword-lib/blob/main/src/helpers/pashword.ts) file to know more about it.

## Algorithmic Considerations
The algorithm generates unique random passwords that always contain symbols, lowercase letters, uppercase letters and numbers. This gives Pashword the ability to generate strong passwords while being cryptographically secure in implementation.

1. At no point is user data saved or sent to a remote server.
2. Userdata is hashed (but I'm calling this encryption on the webapp for easy understanding, so one-way-encryption) first using SHA3-512 and then using scrypt algorithm the second time. This is to ensure maximum bruteforce and dictionary attack protection even with ASICs. This is why scrypt, which is memory and CPU hard algorithm was chosen for the job. You can read more about scrypt [here](https://en.wikipedia.org/wiki/Scrypt).
3. SHAKE-256 is used as a CSPRNG.
4. 256 bit random number is then used to generated indices for where each character in the password goes.
5. The scrypt output is used as the seed for SHAKE CSPRNG. Big Endian byte order is used to convert the 32 bytes into 256 bit big integer.
7. Entropy is as high as possible and suitable for the supposed threat model of Pashword.
8. To highlight again, during any process, no data is stored in any kind of database or cache. Everything happens in realtime and is deleted once user resets the state.

Here's a rough diagram of how `pashword.ts` works:
<img src="/algorithm_illustration.png">

# Development 🧰

Open terminal and enter the following commands:
```bash
# Clone the repository
git clone https://github.com/pashword/pashword.git

# Change Directory
cd pashword

# Install dependencies
npm install

# Run development server
npm run dev
```

# Self-hosting 🤳

Docker support coming soon. Till then, please follow the development instructions to run a local instance.

# FAQ
Please [Read the FAQ](https://pashword.app/#faq) for any security questions or doubts about Pashword.

# Credits ♥

This obviously wouldn't have been possible without the people who helped me with the code review and suggested new ideas for the algorithm. I'm deeply grateful to have an army of big brain people who contributed to the completion of this project. Thanks to nsrCodes, TGS963, dsx724, coyotium and everybody else who helped me with this project :)

#
<div align="center">

**Made by Nayam Amarshe**\
Pashword © 2022
</div>
