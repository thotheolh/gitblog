# How Intel ID Can Enable Persistent Device Identification

### FIDO and Intel Identity Protection
FIDO authentication has been an important milestone in Ientity Protection by incorporating usable hardware
protected tokens and biometrics as a second factor authentication with other traditional authenticators (i.e. PINs and passwords).

Intel have always had an Identity Protection suite that leverages the so-called Trusted Execution Environment (a.k.a Intel SGX) for 'secure storage and transaction' via it's TEE/Intel SGX environment.

Intel has decided to extend it's Identity Protection to ubiquitious multi-factor authentication which includes the ability to use the Identity Protection capability in a 'silent manner'.

### FIDO authenticator crytographic key generation
The FIDO protocol uses ECC cryptography and requires that as a defensive mechanism against the ability to identify and track users across multiple domains via their public keys, unique ECC keypairs have to be generated for every domain as a means to prevent domains from tracking users across multiple domains. The known problem of the scheme acknowledge the fact that actual personal details might be required to be registered with a particular ECC key when setting up authentication for a single domain with FIDO.

### Creation of a hardware-backed persistent backdoor
Most FIDO authentication requires the insertion of a token (FIDO U2F scheme) or the insertion and activation of the token via a biometric authentication or a secret PIN/Password (FIDO UAF scheme). Intel intends to simplify the use of FIDO authenication by leveraging it's hardware-based Identity Protection suite to allow seamless FIDO authentication without requiring a token and to transparently authenticate without the necessity of the user needing to intervent when multi-factor authentication via FIDO scheme is required.

With the use of hardware-backed transparent authentication without user's intervention or even the user's knowledge of the activation of the authentication protocol, this leads to the possibility of a transparent hardware-backed backdoor under the guise as an Identity Protection authenticator within Intel's hardware as the Intel hardware may simply activate the FIDO authentication protocol automatically without the user's knowing which should not occur under the circumstance that a physical token that can be paired with biometrics or a Password/PIN should prevent as the insertion of the physical token or the entry of Password/PIN or usage of biometric (except for facial recognition that can be done surreptitiously) acts as an additional barrier to prevent covert channel communications with possibly subverted hardware or implementations.

The Intel's method of transparent authentication breaks the physical barrier that is suppose to be used to prevent covert channel communication and thus acts as a stepping stone for the leaking of identity and tracing of user across multiple domains.

The only barrier from a theoretical standpoint to prevent multiple domain tracking is the requirement by FIDO Alliance that every domain must use a unique ECC key for authentication. This requirement would be necessary for a FIDO capable certification.

Intel can still comply with the requirements of creating unique ECC keys for every authentication domain while still maintaining tracking of user across multiple domain by using a branch of Crypto-virology (Kleptography) to taint the ECC secret key in a way that not only can Intel retrieve the secret key material from observing the public key but also with the identification of the unique Intel CPU and user by inspecting the seemingly random and unique but tainted ECC public key. Some examples of existing Crypto-virology attacks against Public Key systems (i.e. RSA and ECC) are listed in the links below for referencing which Intel could use if they decide to the taint the ECC keys used for their transparent FIDO authentication capability within their Intel CPUs.

### Prevention of tracebility via transparent authentication problem
The simple way to prevent such a problem presented by Intel's transparent FIDO authentication would be to not use it in the first place but to use physical authenticators where one could remove them when not needed and also preferrably with open source codes and designs. 

In the event that the Intel Identity Protection platform has to be used for FIDO authentication, it would be preferrable to generate your own ECC keypair on a trusted device and import them into the Identity Protection platform.

### Links:
 - https://fidoalliance.org
 - https://www.intel.com/content/dam/www/public/us/en/documents/solution-briefs/banks-seek-to-stop-fraud-in-its-tracks-with-simpler-stronger-authentication-point-of-view.pdf
 - https://www.infosecurity-magazine.com/magazine-features/the-dark-side-of-cryptography-kleptography-in/
 - https://pdfs.semanticscholar.org/a441/bbf0c9849dbc2bf87bad06727bfa96d85a56.pdf
 - http://paper.ijcsns.org/07_book/201006/20100628.pdf
 - https://www.win.tue.nl/eipsi/surveillance/yung.pdf
 - http://www.cryptovirology.com/cryptovfiles/research.html

#### Publication:
 - Author: Thotheolh
 - Date: 28/08/2017