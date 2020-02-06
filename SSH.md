- SSH protocol uses encryption to secure connection between a client and server
- All commands, user authentication, file transfer are encrypted to protect against attacks in the network

Steps in Connection:

1. Client initiates connection by contacting the server
2. SSH server sends a public key
3. Client and server negotiate parameters and open secure channel
4. User login to server host operating system

- An SSH Key is an access credential
- SSH keys allow for automation
- SSH Keys are functionally akin to passwords: they grant access, and control *who* can access *what*.

- Authorized keys are **public keys** that grant access. They're like locks. Anyone can see a lock, but only certain people have the correct key to gain access.
- **Private keys** are what grant you access (your personal key to the lock).

**Public keys**: Lock on a door. People can see it's there, but they can't access it without the proper key.
**Private keys**: Your key that unlocks the door.

- **Identity keys** -- private keys that an SSH client uses to authenticate itself when logging into an SSH server.

Private key = locked door to the office
Public keys = keys that unlock the office
Identity key = Gareth's key, that when placed in the locked office door authenticates Gareth as a valid user and grants access to the office. (i.e. my specific key)

- Authorized keys and Identity keys are jointly called *user keys* because they relate to user authentication (as opposed to host keys, which validate host authentication)

- *Session keys*
  - SSH uses a key exchange algorithm to derive unique keys for each session or connection between client and server.
    - Some algorithms generate a shared secret that is only known to the client and the server; however, this is vulnerable to man-in-the-middle attacks. It's vulnerable because a third-party could get in between the client and server and pretend to be the respective side -- functionally establishing an independent connection to both the client and the server.
    - To prevent these kinds of attacks, key exchanges typically include some kind of authentication --> generally a digital signature of all data exchanged during the key exchange, as seen by the signing party. The data is then signed by some shared secret -- often a private key. The other end then verifies the signature with a public key.






Resources:
- https://www.ssh.com/ssh