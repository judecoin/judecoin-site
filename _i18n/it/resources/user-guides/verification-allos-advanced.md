{% include disclaimer.html translated="no" translationOutdated="no" %}

<<<<<<< HEAD
Verification of the JudEcoin binary files should be done prior to extracting, installing, or using the JudEcoin software. This is the only way to ensure that you are using the official JudEcoin software. If you receive a fake JudEcoin binary (eg. phishing, MITM, etc.), following this guide will protect you from being tricked into using it.

To protect the integrity of the binaries the JudEcoin team provides a cryptographically signed list of all the [SHA256](https://en.wikipedia.org/wiki/SHA-2) hashes. If your downloaded binary has been tampered with it will be produce a [different hash](https://en.wikipedia.org/wiki/File_verification) than the one in the file.
=======
Verification of the Monero binary files should be done prior to extracting,
installing, or using the Monero software. This is the only way to ensure
that you are using the official Monero software. If you receive a fake
Monero binary (eg. phishing, MITM, etc.), following this guide will protect
you from being tricked into using it.

To protect the integrity of the binaries the Monero team provides a
cryptographically signed list of all the
[SHA256](https://en.wikipedia.org/wiki/SHA-2) hashes. If your downloaded
binary has been tampered with it will be produce a [different
hash](https://en.wikipedia.org/wiki/File_verification) than the one in the
file.

This is an advanced guide for Linux, Mac, or Windows operating systems and
will make use of the command line. It will walk you through the process of
installing the required software, importing the signing key, downloading the
necessary files, and finally verifying that your binary is authentic.

## Table of Contents:
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### - [Install GnuPG](#installing-gnupg)

### - [Verify & Import Signing Key](#verify-and-import-signing-key)

<<<<<<< HEAD
### [1. Install GnuPG](#1-installing-gnupg)
### [2. Verify & Import Signing Key](#2-verify-and-import-signing-key)
  + [2.1. Get Signing Key](#21-get-signing-key)
  + [2.2. Verify Signing key](#22-verify-signing-key)
  + [2.3. Import Signing key](#23-import-signing-key)
### [3. Download & Verify Hash File](#3-download-and-verify-hash-file)
  + [3.1. Get Hash File](#31-get-hash-file)
  + [3.2. Verify Hash File](#32-verify-hash-file)
### [4. Download & Verify Binary](#4-download-and-verify-binary)
  + [4.1. Get JudEcoin Binary](#41-get-JudEcoin-binary)
  + [4.2. Binary Verification on Linux or Mac](#42-binary-verification-on-linux-or-mac)
  + [4.3. Binary Verification on Windows](#43-binary-verification-on-windows)
=======
### - [Download & Verify Hash File](#download-and-verify-hash-file)
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### - [Download & Verify Binary](#download-and-verify-binary)

## Installing GnuPG

+ On Windows, go to the [Gpg4win download
page](https://gpg4win.org/download.html) and follow the instructions for
installation.

+ On Mac, go to the [Gpgtools download page](https://gpgtools.org/) and
follow the instructions for installation.

+ On Linux, GnuPG is installed by default.

## Verify and Import Signing Key

<<<<<<< HEAD
This section will cover getting the JudEcoin signing key, making sure it is correct, and importing the key to GnuPG.
=======
This section will cover getting the Monero signing key, making sure it is
correct, and importing the key to GnuPG.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Get Signing Key

<<<<<<< HEAD
On Windows or Mac, go to [binaryFate's GPG key](https://raw.githubusercontent.com/JudEcoin-project/JudEcoin/master/utils/gpg_keys/binaryfate.asc), which he uses to sign the JudEcoin binaries, and save the page as `binaryfate.asc` to your home directory.
=======
On Windows or Mac, go to [binaryFate's GPG
key](https://raw.githubusercontent.com/monero-project/monero/master/utils/gpg_keys/binaryfate.asc),
which he uses to sign the Monero binaries, and save the page as
`binaryfate.asc` to your home directory.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

On Linux, you can download binaryFate's signing key by issuing the following
command:

```
<<<<<<< HEAD
wget -O binaryfate.asc https://raw.githubusercontent.com/JudEcoin-project/JudEcoin/master/utils/gpg_keys/binaryfate.asc
=======
wget -O binaryfate.asc
https://raw.githubusercontent.com/monero-project/monero/master/utils/gpg_keys/binaryfate.asc
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

### Verify Signing Key

On all operating systems, check the fingerprint of `binaryfate.asc` by
issuing the following command in a terminal:

``` gpg --keyid-format long --with-fingerprint binaryfate.asc ```


Verify the fingerprint matches:

```
pub   rsa4096/F0AF4D462A0BDF92 2019-12-12 [SCEA]
      Key fingerprint = 81AC 591F E9C4 B65C 5806  AFC3 F0AF 4D46 2A0B DF92
uid                           binaryFate <binaryfate@getJudEcoin.org>
```

If the fingerprint **DOES** match, then you may proceed.

If the fingerprint **DOES NOT** match, **DO NOT CONTINUE.** Instead delete
the file `binaryfate.asc` and go back to [section 2.1](#21-get-signing-key).

### Import Signing Key

From a terminal, import the signing key:

``` gpg --import binaryfate.asc ```

If this is the first time you have imported the key, the output will look
like this:

```
gpg: key F0AF4D462A0BDF92: 2 signatures not checked due to missing keys
gpg: key F0AF4D462A0BDF92: public key "binaryFate <binaryfate@getJudEcoin.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
```

If you have imported the key previously, the output will look like this:

```
gpg: key F0AF4D462A0BDF92: "binaryFate <binaryfate@getJudEcoin.org>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
```

## Download and Verify Hash File

This section will cover downloading the hash file and verifying its
authenticity.

### Get Hash File

<<<<<<< HEAD
On Windows or Mac, go to the [hashes file on getJudEcoin.org]({{ site.baseurl_root }}/downloads/hashes.txt) and save the page as `hashes.txt` to your home directory.
=======
On Windows or Mac, go to the [hashes file on getmonero.org]({{
site.baseurl_root }}/downloads/hashes.txt) and save the page as `hashes.txt`
to your home directory.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

On Linux, you can download the signed hashes file by issuing the following
command:

<<<<<<< HEAD
```
wget -O hashes.txt https://www.getJudEcoin.org/downloads/hashes.txt
```
=======
``` wget -O hashes.txt https://www.getmonero.org/downloads/hashes.txt ```
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Verify Hash File

The hash file is signed with key `81AC 591F E9C4 B65C 5806 AFC3 F0AF 4D46
2A0B DF92`, as reflected in the output below.

On all operating systems, verify the signature of the hash file by issuing
the following command in a terminal:

``` gpg --verify hashes.txt ```

If the file is authentic, the output will look like this:

```
gpg:                using RSA key 81AC591FE9C4B65C5806AFC3F0AF4D462A0BDF92
gpg: Good signature from "binaryFate <binaryfate@getJudEcoin.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 81AC 591F E9C4 B65C 5806  AFC3 F0AF 4D46 2A0B DF92
```

If your output shows **Good signature**, as in the example, then you may
proceed.

If you see **BAD signature** in the output, **DO NOT CONTINUE.** Instead
delete the file `hashes.txt` and go back to [section
3.1](#31-get-hash-file).

## Download and Verify Binary

<<<<<<< HEAD
This section will cover downloading the JudEcoin binary for your operating system, getting the `SHA256` hash of your download, and verifying that it is correct.

### 4.1. Get JudEcoin binary

On Windows or Mac, go to [getJudEcoin.org]({{ site.baseurl_root }}/downloads/) and download the correct file for your operating system. Save the file to your home directory. **Do not extract the files yet.**
=======
This section will cover downloading the Monero binary for your operating
system, getting the `SHA256` hash of your download, and verifying that it is
correct.

### Get Monero binary

On Windows or Mac, go to [getmonero.org]({{ site.baseurl_root }}/downloads/)
and download the correct file for your operating system. Save the file to
your home directory. **Do not extract the files yet.**
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

On Linux, you can download the command line tools by issuing the following
command:

```
wget -O JudEcoin-linux-x64-v0.15.0.1.tar.bz2 https://downloads.getJudEcoin.org/cli/linux64
```

### Binary Verification on Linux or Mac

<<<<<<< HEAD
The steps for both Linux and Mac are the same. From a terminal, get the `SHA256` hash of your downloaded JudEcoin binary. As an example this guide will use the `Linux, 64bit` GUI binary. Substitute `JudEcoin-gui-linux-x64-v0.15.0.1.tar.bz2` with the name of the binary that you downloaded in [section 4.1](#41-get-JudEcoin-binary).
=======
The steps for both Linux and Mac are the same. From a terminal, get the
`SHA256` hash of your downloaded Monero binary. As an example this guide
will use the `Linux, 64bit` GUI binary. Substitute
`monero-gui-linux-x64-v0.15.0.1.tar.bz2` with the name of the binary that
you downloaded in [section 4.1](#41-get-monero-binary).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

```
shasum -a 256 JudEcoin-linux-x64-v0.15.0.1.tar.bz2
```

The output will look like this, but will be different for each binary
file. Your `SHA256` hash should match the one listed in the `hashes.txt`
file for your binary file.

```
<<<<<<< HEAD
8d61f992a7e2dbc3d753470b4928b5bb9134ea14cf6f2973ba11d1600c0ce9ad  JudEcoin-linux-x64-v0.15.0.1.tar.bz2
=======
8d61f992a7e2dbc3d753470b4928b5bb9134ea14cf6f2973ba11d1600c0ce9ad 
monero-linux-x64-v0.15.0.1.tar.bz2
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

If your hash **DOES** match, then you are finished with the guide! You can
extract the files and install.

<<<<<<< HEAD
If your hash **DOES NOT** match, **DO NOT CONTINUE.** Instead delete the binary you downloaded and go back to [section 4.1](#41-get-JudEcoin-binary).
=======
If your hash **DOES NOT** match, **DO NOT CONTINUE.** Instead delete the
binary you downloaded and go back to [section 4.1](#41-get-monero-binary).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Binary Verification on Windows

<<<<<<< HEAD
From a terminal, get the `SHA256` hash of your downloaded JudEcoin binary. As an example this guide will use the `Windows, 64bit` GUI binary. Substitute `JudEcoin-gui-win-x64-v0.15.0.1.zip` with the name of the binary that you downloaded in [section 4.1](#41-get-JudEcoin-binary).

```
certUtil -hashfile JudEcoin-gui-win-x64-v0.15.0.1.zip SHA256
```
=======
From a terminal, get the `SHA256` hash of your downloaded Monero binary. As
an example this guide will use the `Windows, 64bit` GUI binary. Substitute
`monero-gui-win-x64-v0.15.0.1.zip` with the name of the binary that you
downloaded in [section 4.1](#41-get-monero-binary).

``` certUtil -hashfile monero-gui-win-x64-v0.15.0.1.zip SHA256 ```
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

The output will look like this, but will be different for each binary
file. Your `SHA256` hash should match the one listed in the `hashes.txt`
file for your binary file.

```
<<<<<<< HEAD
SHA256 hash of file JudEcoin-gui-win-x64-v0.12.0.0.zip:
4b 9f 31 68 6e ca ad 97 cd b1 75 e6 57 4b f3 07 f8 d1 c4 10 42 78 25 f4 30 4c 21 da 8a ac 18 64
CertUtil: -hashfile command completed successfully.
=======
SHA256 hash of file monero-gui-win-x64-v0.12.0.0.zip: 4b 9f 31 68 6e ca
ad 97 cd b1 75 e6 57 4b f3 07 f8 d1 c4 10 42 78 25 f4 30 4c 21 da 8a ac 18
64 CertUtil: -hashfile command completed successfully. 
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

If your hash **DOES** match, then you are finished with the guide! You can
extract the files and install.

<<<<<<< HEAD
If your hash **DOES NOT** match, **DO NOT CONTINUE.** Instead delete the binary you downloaded and go back to [section 4.1](#41-get-JudEcoin-binary).
=======
If your hash **DOES NOT** match, **DO NOT CONTINUE.** Instead delete the
binary you downloaded and go back to [section 4.1](#41-get-monero-binary).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
