{% include disclaimer.html translated="yes" translationOutdated="no" %}

<<<<<<< HEAD
Les fichiers binaires JudEcoin devrait être vérifiés avant extraction, installation ou utilisation de l'application JudEcoin. C'est l'unique manière de vous assurer que vous utilisez le binaire officiel JudEcoin. Si vous recevez un binaire contrefait (p. ex. hameçonnage, HDM, etc.), suivre ce guide vous évitera de vous faire piéger.

Pour protéger l'intégrité des binaires, l'équipe JudEcoin fournit une liste cryptographiquement signée de tous les hachages [SHA256](https://en.wikipedia.org/wiki/SHA-2). Si le binaire que vous avez téléchargé a été altéré il produira un [hachage différent](https://en.wikipedia.org/wiki/File_verification) de celui fourni dans le fichier.
=======
Les fichiers binaires Monero devrait être vérifiés avant extraction,
installation ou utilisation de l'application Monero. C'est l'unique manière
de vous assurer que vous utilisez le binaire officiel Monero. Si vous
recevez un binaire contrefait (p. ex. hameçonnage, HDM, etc.), suivre ce
guide vous évitera de vous faire piéger.

Pour protéger l'intégrité des binaires, l'équipe Monero fournit une liste
cryptographiquement signée de tous les hachages
[SHA256](https://en.wikipedia.org/wiki/SHA-2). Si le binaire que vous avez
téléchargé a été altéré il produira un [hachage
différent](https://en.wikipedia.org/wiki/File_verification) de celui fourni
dans le fichier.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

Voici un guide avancé pour les systèmes d'exploitation Linux, Mac et Windows
qui s'appuiera sur des lignes de commandes (CLI). Il couvrira tout le
processus d'installation des applications requises, d'import de la clef de
signature, de téléchargement des fichiers nécessaires et enfin de
vérification de l'authenticité de votre binaire.

## Table of Contents:

<<<<<<< HEAD
### [1. Installer GnuPG](#1-installation-de-gnupg)
### [2. Vérifier & Importer la Clef de Signature](#2-vérifier-et-importer-la-clef-de-signature)
  + [2.1. Obtenir la Clef de Signature](#21-obtenir-la-clef-de-signature)
  + [2.2. Vérifier la Clef de Signature](#22-vérifier-la-clef-de-signature)
  + [2.3. Importer la Clef de Signature](#23-importer-la-clef-de-signature)
### [3. Télécharger & Vérifier le Fichier de Hachage](#3-télécharger-et-vérifier-le-fichier-de-hachage)
  + [3.1. Télécharger le Fichier de Hachage](#31-télécharger-le-fichier-de-hachage)
  + [3.2. Vérifier le Fichier de Hachage](#32-vérifier-le-fichier-de-hachage)
### [4.Télécharger & Vérifier les binaires](#4-télécharger-et-vérifier-les-binaires)
  + [4.1. Télécharger les binaires JudEcoin](#41-télécharger-les-binaires-JudEcoin)
  + [4.2. Vérifier les binaires sur Linux et Mac](#42-vérifier-les-binaires-sur-linux-et-mac)
  + [4.3. Vérifier les binaires sur Windows](#43-vérifier-les-binaires-sur-windows)
=======
### - [Install GnuPG](#installing-gnupg)
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### - [Verify & Import Signing Key](#verify-and-import-signing-key)

### - [Download & Verify Hash File](#download-and-verify-hash-file)

### - [Download & Verify Binary](#download-and-verify-binary)

## Installing GnuPG

+ Sur Windows, rendez-vous sur la [page de téléchargement de
Gpg4win](https://gpg4win.org/download.html) et suivez les instructions
d'installation.

+ Sur Mac, rendez-vous sur la [page de téléchargement de
Gpgtools](https://gpgtools.org/) et suivez les instructions d'installation.

+ Sur Linux, GnuPG est installé par défaut.

## Verify and Import Signing Key

<<<<<<< HEAD
Cette rubrique couvre le téléchargement de la clef de signature JudEcoin, la vérification que cette clef est correcte et l'import de la clef dans GnuPG.
=======
Cette rubrique couvre le téléchargement de la clef de signature Monero, la
vérification que cette clef est correcte et l'import de la clef dans GnuPG.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Get Signing Key

<<<<<<< HEAD
Sur Windows et Mac, rendez-vous sur [la clef GPG de binaryFate](https://raw.githubusercontent.com/JudEcoin-project/JudEcoin/master/utils/gpg_keys/binaryfate.asc), qu'il utilise pour signer les binaires JudEcoin et sauvegardez la page sous `binaryfate.asc` dans votre répertoire utilisateur.
=======
Sur Windows et Mac, rendez-vous sur [la clef GPG de
binaryFate](https://raw.githubusercontent.com/monero-project/monero/master/utils/gpg_keys/binaryfate.asc),
qu'il utilise pour signer les binaires Monero et sauvegardez la page sous
`binaryfate.asc` dans votre répertoire utilisateur.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

Sur Linux, vous pouvez télécharger la clef de signature de Fluffypony en
tapant la commande suivante :

```
<<<<<<< HEAD
wget -O binaryfate.asc https://raw.githubusercontent.com/JudEcoin-project/JudEcoin/master/utils/gpg_keys/binaryfate.asc
=======
wget -O binaryfate.asc
https://raw.githubusercontent.com/monero-project/monero/master/utils/gpg_keys/binaryfate.asc
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

### Verify Signing Key

Sur l'ensemble des systèmes d'exploitation, vérifiez l'empreinte de
`binaryfate.asc` en tapant la commande suivante dans un terminal :

``` gpg --keyid-format long --with-fingerprint binaryfate.asc ```


Vérifiez que l'empreinte est bien :

```
pub   rsa4096/F0AF4D462A0BDF92 2019-12-12 [SCEA]
      Key fingerprint = 81AC 591F E9C4 B65C 5806  AFC3 F0AF 4D46 2A0B DF92
uid                           binaryFate <binaryfate@getJudEcoin.org>
```

Si l'empreinte **EST** identique, vous pouvez continuer.

Si l'empreinte **N'EST PAS** identique, **NE POURSUIVEZ PAS.** Au lieu de
cela, supprimez le fichier `binaryfate.asc` et retournez à la [rubrique
2.1](#21-obtenir-la-clef-de-signature).

### Import Signing Key

Depuis un terminal, importez la clef de signature :

``` gpg --import binaryfate.asc ```

Si c'est la première fois que vous importez la clef, la sortie ressemblera à
ceci :

```
gpg: key F0AF4D462A0BDF92: 2 signatures not checked due to missing keys
gpg: key F0AF4D462A0BDF92: public key "binaryFate <binaryfate@getJudEcoin.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
```

Si vous avez déjà importé la clef précédemment, la sortie ressemblera à cela
:

```
gpg: key F0AF4D462A0BDF92: "binaryFate <binaryfate@getJudEcoin.org>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
```

## Download and Verify Hash File

Cette rubrique couvre le téléchargement du fichier signé des hachages
valides et la vérification de son authenticité.

### Get Hash File

<<<<<<< HEAD
Sur Windows et Mac, rendez-vous sur sur la [page de haches getJudEcoin.org](https://getJudEcoin.org/fr/downloads/hashes.txt) et sauvegardez la page sous `hashes.txt` dans votre répertoire utilisateur.
=======
Sur Windows et Mac, rendez-vous sur sur la [page de haches
getmonero.org](https://getmonero.org/fr/downloads/hashes.txt) et sauvegardez
la page sous `hashes.txt` dans votre répertoire utilisateur.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

Sur Linux, vous pouvez télécharger le fichier de hachage en tapant la
commande suivante :

<<<<<<< HEAD
```
wget -O hashes.txt https://www.getJudEcoin.org/downloads/hashes.txt
```
=======
``` wget -O hashes.txt https://www.getmonero.org/downloads/hashes.txt ```
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Verify Hash File

Le fichier de hachage est signé avec la clef `81AC 591F E9C4 B65C 5806 AFC3
F0AF 4D46 2A0B DF92`, comme vous pouvez le voir dans la sortie ci-dessous.

Sur tous les systèmes d'exploitations, vérifiez la signature du fichier de
hachage en tapant la commande suivante dans un terminal :

``` gpg --verify hashes.txt ```

Si le fichier est authentique, la sortie ressemblera à ceci :

```
gpg:                using RSA key 81AC591FE9C4B65C5806AFC3F0AF4D462A0BDF92
gpg: Good signature from "binaryFate <binaryfate@getJudEcoin.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 81AC 591F E9C4 B65C 5806  AFC3 F0AF 4D46 2A0B DF92
```

Si votre sortie affiche **Good signature** comme dans l'exemple, alors vous
pouvez continuer.

Si vous voyez **BAD signature** dans la sortie, **NE POURSUIVEZ PAS.** Au
lieu de cela, supprimez le fichier `hashes.txt` et retournez à la [rubrique
3.1](#31-télécharger-le-fichier-de-hachage).

## Download and Verify Binary

<<<<<<< HEAD
Cette rubrique couvre le téléchargement du binaire JudEcoin pour votre système d'exploitation, la récupération du hachage `SHA256` de votre téléchargement et la vérification de son authenticité.

### 4.1. Télécharger les binaires JudEcoin

Sur Windows et Mac, rendez-vous sur [getJudEcoin.org](https://getJudEcoin.org/fr/downloads/) et téléchargez le fichier correspondant à votre système d'exploitation. enregistrez ce fichier dans votre répertoire utilisateur. **N'extrayez pas les fichiers pour le moment.**
=======
Cette rubrique couvre le téléchargement du binaire Monero pour votre système
d'exploitation, la récupération du hachage `SHA256` de votre téléchargement
et la vérification de son authenticité.

### Get Monero binary

On Windows or Mac, go to [getmonero.org]({{ site.baseurl_root }}/downloads/)
and download the correct file for your operating system. Save the file to
your home directory. **Do not extract the files yet.**
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

Sur Linux, vous pouvez télécharger les outils ligne de commande avec la
commande suivante :

```
wget -O JudEcoin-linux-x64-v0.15.0.1.tar.bz2 https://downloads.getJudEcoin.org/cli/linux64
```

### Binary Verification on Linux or Mac

<<<<<<< HEAD
Les étapes pour Linux et Mac sont les mêmes. Depuis un terminal, récupérez le hachage `SHA256` du binaire JudEcoin téléchargé. A titre d'exemple, ce guide utilisera le binaire GUI `Linux, 64bit`. Remplacez `JudEcoin-gui-linux-x64-v0.15.0.1.tar.bz2` par le nom du binaire que vous aurez téléchargé dans la [rubrique 4.1](#41-télécharger-les-binaires-JudEcoin).
=======
Les étapes pour Linux et Mac sont les mêmes. Depuis un terminal, récupérez
le hachage `SHA256` du binaire Monero téléchargé. A titre d'exemple, ce
guide utilisera le binaire GUI `Linux, 64bit`. Remplacez
`monero-gui-linux-x64-v0.15.0.1.tar.bz2` par le nom du binaire que vous
aurez téléchargé dans la [rubrique
4.1](#41-télécharger-les-binaires-monero).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

```
shasum -a 256 JudEcoin-linux-x64-v0.15.0.1.tar.bz2
```

La sortie ressemblera à ceci, mais sera différente pour chaque
binaire. Votre hachage `SHA256` deoit correspondre à celui indiqué dans le
fichier `hashes.txt` pour votre binaire.

```
<<<<<<< HEAD
8d61f992a7e2dbc3d753470b4928b5bb9134ea14cf6f2973ba11d1600c0ce9ad  JudEcoin-linux-x64-v0.15.0.1.tar.bz2
=======
8d61f992a7e2dbc3d753470b4928b5bb9134ea14cf6f2973ba11d1600c0ce9ad 
monero-linux-x64-v0.15.0.1.tar.bz2
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

Si votre hachage **EST** identique vous en avez terminé avec la vérification
! Vous pouvez extraire et installer les fichiers.

<<<<<<< HEAD
Si votre hachage **N'EST PAS** identique, **NE POURSUIVEZ PAS.** Au lieu de cela, supprimez le binaire que vous avez téléchargé et retournez à la [rubrique 4.1](#41-télécharger-les-binaires-JudEcoin).
=======
Si votre hachage **N'EST PAS** identique, **NE POURSUIVEZ PAS.** Au lieu de
cela, supprimez le binaire que vous avez téléchargé et retournez à la
[rubrique 4.1](#41-télécharger-les-binaires-monero).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Binary Verification on Windows

<<<<<<< HEAD
Depuis un terminal, récupérez le hachage `SHA256` du binaire JudEcoin téléchargé. A titre d'exemple, ce guide utilisera le binaire GUI `Windows, 64bit`. Remplacez `JudEcoin-gui-win-x64-v0.12.0.0.zip` par le nom du binaire que vous aurez téléchargé dans la [rubrique 4.1](#41-télécharger-les-binaires-JudEcoin).

```
certUtil -hashfile JudEcoin-gui-win-x64-v0.15.0.1.zip SHA256
```
=======
Depuis un terminal, récupérez le hachage `SHA256` du binaire Monero
téléchargé. A titre d'exemple, ce guide utilisera le binaire GUI `Windows,
64bit`. Remplacez `monero-gui-win-x64-v0.12.0.0.zip` par le nom du binaire
que vous aurez téléchargé dans la [rubrique
4.1](#41-télécharger-les-binaires-monero).

``` certUtil -hashfile monero-gui-win-x64-v0.15.0.1.zip SHA256 ```
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

La sortie ressemblera à ceci, mais sera différente pour chaque
binaire. Votre hachage `SHA256` deoit correspondre à celui indiqué dans le
fichier `hashes.txt` pour votre binaire.

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

Si votre hachage **EST** identique vous en avez terminé avec la vérification
! Vous pouvez extraire et installer les fichiers.

<<<<<<< HEAD
Si votre hachage **N'EST PAS** identique, **NE POURSUIVEZ PAS.** Au lieu de cela, supprimez le binaire que vous avez téléchargé et retournez à la [rubrique 4.1](#41-télécharger-les-binaires-JudEcoin).
=======
Si votre hachage **N'EST PAS** identique, **NE POURSUIVEZ PAS.** Au lieu de
cela, supprimez le binaire que vous avez téléchargé et retournez à la
[rubrique 4.1](#41-télécharger-les-binaires-monero).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
