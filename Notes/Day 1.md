# 57. WIRELESS SECURITY

INTRO TO WIRELESS NETWORK SECURITY

- Although SECURITY is important in ALL NETWORKS, it is even more essential in WIRELESS NETWORKS
- Because WIRELESS SIGNALS are not contained within a WIRE, any DEVICE within range of the signal can receive traffic
- In WIRED NETWORKS, traffic is often only ENCRYPTED when sent over an UNTRUSTED NETWORK such as the INTERNET
- In WIRELESS NETWORKS, it is VERY important to ENCRYPT traffic sent between the WIRELESS CLIENTS and the AP

- We will cover THREE MAIN CONCEPTS:
    - AUTHENTICATION
    - ENCRYPTION
    - INTEGRITY

---

AUTHENTICATION

- All CLIENTS must be AUTHENTICATED before they can associate with an AP
- In a corporate setting, only TRUSTED USERS / DEVICES should be given ACCESS to the NETWORK
    - In corporate settings, a separate SSID which doesn’t have ACCESS to the corporate NETWORK can be provided for GUEST USERS
- Ideally, CLIENTS should also AUTHENTICATE the AP to avoid associating with a malicious AP
- There are MULTIPLE WAYS to AUTHENTICATE:
    - PASSWORD
    - USERNAME / PASSWORD
    - CERTIFICATES

![image](https://github.com/psaumur/CCNA/assets/106411237/00d34740-8da7-428d-8b36-f8998ec2f0cd)

---

ENCRYPTION

- Traffic sent between CLIENTS and APs should be ENCRYPTED so that it can’t be read by anyone except the AP and the CLIENT
- There are many possible PROTOCOLS that can be used to ENCRYPT traffic
- All DEVICES on the WLAN will use the same PROTOCOL, however each CLIENT will use a unique ENCRYPTION / DECRYPTION KEY so that other DEVICES can’t read its traffic
- A “GROUP KEY” is used by the AP to ENCRYPT traffic that it wants to send to all of its clients
    - All of the CLIENTS associated with the AP keep that key so they can DECRYPT the traffic
    

---

INTEGRITY

- As explained in the “SECURITY FUNDAMENTALS” video of the course, INTEGRITY ensures that the message is not modified by a third-party
- The message that is sent by the SOURCE HOST should be the same as the message that is received by the DESTINATION HOST
- A MIC (Message Integrity Check) is added to the message to help protect their INTEGRITY.

![image](https://github.com/psaumur/CCNA/assets/106411237/b632c321-36e5-4a03-b08c-d0a2c2e215da)

---

AUTHENTICATION METHODS

The original 802.11 STANDARD included TWO OPTIONS for AUTHENTICATION:

- OPEN AUTHENTICATION
    - The CLIENT sends an AUTHENTICATION REQUEST and the AP just accepts it
    - The is clearly NOT a SECURE AUTHENTICATION method
    - After the CLIENT is AUTHENTICATED and associated with the AP, it’s possible to require the USER to AUTHENTICATE via other methods before ACCESS to the NETWORK is granted (ie: Starbucks WI-FI)
- WEP (Wired Equivalent Privacy)
    - WEP is used to provide both AUTHENTICATION and ENCRYPTION of WIRELESS traffic
    - For ENCRYPTION, WEP uses the RC4 ALGORITHM
    - WEP is a “SHARED-KEY” PROTOCOL, requiring the SENDER and RECEIVER to have the same KEY
    - WEP KEYS can be 40 bits or 104 bits in length
    - The above KEYS are combined with a 24-bit “IV” (INITIALIZATION VECTOR) to bring the total length to 64 bits or 128 bits
    - WEP ENCRYPTION is NOT SECURE and can easily be cracked
    - WEP can be used for AUTHENTICATION like this:
    

![image](https://github.com/psaumur/CCNA/assets/106411237/86e4f243-1692-41a6-9b15-6b2e99942e50)

---

EAP (Extensible Authentication Protocol)

- EAP is an AUTHENTICATION FRAMEWORK
- It defines a STANDARD SET of AUTHENTICATION FUNCTIONS that are used by the various *EAP METHODS*
- We will look at FOUR EAP METHODS:
    - LEAP
    - EAP-FAST
    - PEAP
    - EAP-TLS
- EAP is integrated with **802.1X** which provides *PORT-BASED NETWORK ACCESS CONTROL*

**802.1X** is used to limit NETWORK ACCESS for CLIENTS connected to a LAN or WLAN until they AUTHENTICATE

There are **THREE MAIN ENTITIES** in 802.1X:

- SUPPLICANT : The DEVICE that wants to connect to the NETWORK
- AUTHENTICATOR : The DEVICE that provides access to the NETWORK
- AUTHENTICATION SERVER (AS) : The DEVICE that receives CLIENT credentials and PERMITS / DENIES ACCESS

![image](https://github.com/psaumur/CCNA/assets/106411237/5565e646-696f-4245-b1e5-d728fe0e3380)

- LEAP (Lightweight EAP)
    - LEAP was developed by Cisco an an improvement over WEP
    - CLIENTS must provide a USERNAME and PASSWORD to AUTHENTICATE
    - In addition, *MUTUAL AUTHENTICATION* is provided by both the CLIENT and SERVER sending a CHALLENGE PHRASE to each other.
    - DYNAMIC WEP KEYS are used, meaning that the WEP KEYS are changed frequently
    - Like WEP, LEAP is considered vulnerable and should not be used anymore

![image](https://github.com/psaumur/CCNA/assets/106411237/0b9ecce2-4219-42d0-8275-086b92134cda)

- EAP-FAST (EAP FLEXIBLE AUTHENTICATION via SECURE TUNNELING)
    - EAP-FAST was also developed by Cisco
    - Consists of THREE PHASES:
        - A PAC (PROTECTED ACCESS CREDENTIAL) is generated and passed from SERVER to CLIENT
        - A SECURE TLS 
