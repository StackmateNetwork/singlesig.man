# singlesig.man

The document attempts to cover all the possible methods of backing up single sig bitcoin wallets and their associated trade offs.

## Glossary of Terms

The following terms will be used throughout this document and have the following meaning:

1. Seed: Your root private key which is the result of hashing your mnemonic key material which is the SeedWords + optional Passphrase. This is the access to your wallet. Any change in SeedWords or Passphrase will lead to a new Seed and thereby a new wallet.
2. SeedWords: 12/24 words that make up the primary mnemonic interface to your seed (compulsory).
3. Passphrase: Additional entropy which is combined with your seed phrase to create your seed (optional).
4. Encryption/Decryption: The process of converting information or data into a non-readable code/cipher using an EncryptionKey; especially to prevent unauthorized access. The reverse process of Decryption, will retreive the original contents using the same EncryptionKey. Encryption converts PlainText to a Cipher. Decryption converts a Cipher to PlainText.
5.  PlainText: Ordinary readable text, like this document.
6. Cipher: Non-readable text created as a result of encrypting PlainText.
7. Splits: Breaking down content into parts. For example, the content '879238474' can be split into 3 parts as: '879' + '238 + '474'. Shamir Secret Shares is a more advanced form of Splits where the original contents can be recreated with only a certain threshold of shares, for example 3/5 shares can be used to recreate the original content.

We breakdown options into 2 main categories based on Mnemonic Material. 

- Tier 1: SeedWords only
- Tier 2: SeedWords + Passphrase

We further add 2 subcategories for Mnemonic Material Format (in addition to standard PlainText):

- Plain
- Ciphers

Within each category we look at 3 subcategories regarding the backup options. 

- Memory Only (Zero Physical Backups)
- Single Location (Remote Only / Local Only)
- Geo Distributed (Remote Only / Combo)

`Remote Only Backups means Mnemonic Material is stored in a location away from the inviduals residence i.e. requires travel to access. This provides a good degree of protection against armed robbery since unlocking these wallets will require travel. Best for Savings Accounts.`


`Local Backups provide convenience / ease of use. Better for Current Accounts.`

We also consider the following attack vectors:
- Loss of Backup: Protection via making redundant backups
- Leak of Backup: Protection via using Passphrase
- Armed Robbery: Threats minimized with decoy wallets & Remote Only backups.
- Death of Individual: Requires family planning

## TIER 1:  SeedWords Only

`Common setup for beginners due to simplicity. Generally not recommended for large funds. `

### Plain vs Ciphers
This Tier will only use PlainText backups. Encryption is not recommended for this tier as it requires management of an EncryptionKey.

### Memory Only

`For hardcore users only!`

This type of wallet should generally never be used as your Savings. It makes for a great transit wallet, if you need to use in cases of emergency. Since no physical backups exist, there is not threat of Leak of Mnemonic Material therefore no need for a passphrase. The last word of your SeedWords can be swapped with another word from the BIP39 list to create decoys and get the effect of a Passphrase.

### Single Location 

`Main disadvantage is Loss of Backup.`

If one location is compromised, funds are lost forever.

###### Remote Only

Since we consider that Tier 1 will never hold large funds, this backup mechanism is almost always pointless for this Tier.

###### Local

`Bare minimum backup required for a beginner.`

### Geo Distributed

`Main disadvantage is Leak of Backup.`

`Main advantage is protection against Loss of Backup.`

With every copy of the SeedWords, the chance of leak increases. So when opting into Geo Distribution for a this Tier, we recommend creating only 2-3 copies at most.

###### Remote Only

Since we consider that Tier 1 will never hold large funds, this backup mechanism is almost always pointless for this Tier.

###### Combo
`Best case for a beginner in this Tier.`
Common practice is for an individual to keep one copy of their seed, and share another copy with a close family member. 


## TIER 2:  SeedWords + PassPhrase
`The most flexible and secure single sig setup.`
It is important to note that in all backup methods for this Tier, the passphrase must not be written down - for maximum benfit from the advantages of having a passphrase. At most, a hint can be written down.
A weak and memorable passphrase in all cases is better than no passphrase at all; however, it is only a matter of time, that a wallet created with a weak passphrase is also compromised, although it still buys you some time.

Read the section on Passphrase Tips and Memory for more help with getting this right!

### Plain vs Ciphers

We highly recommend using encryption as a norm in this Tier!

Since users are using a passphrase, the same passphrase can be used as the Encryption Key which will ensure that backups never have to be made in plain text. 

This now eliminates the viablity for any form of Single Location backup and allows maximum redundancy with Geo Distributed backups since encrypted backups will not be compromised in the event of Loss of Mnemonic Material.

### Memory Only

This method makes most sense for Tier 1 only. Addition of a passphrase does not add any advantage here.

### Geo Distributed

Without encryption Geo Distributed backups have to be minimized to protect against Leak of Backups. With encryption however, backups can be shared with multiple people, however, still, care should be taken to only share it as physical copies with friends and family. Since, it is likely that many users will use weak passphrases, it we STRONGLY RECOMMEND AGAINST digital backups as in case of a leak, they can be bruteforced easily.

###### Remote Only

`Recommended option to protect Savings from armed robbery.`

By not storing a backup locally, your attacker cannot through any amount of force, steal your funds. 

###### Combo

`Standard Case`.

Common practice is for an individual to keep one copy of their seed, and share another copy with friends and family. 

## TIPS

### Passphrase

We recommend using a section from a book (hashed) as your passphrase. You can then write down the hint as a puzzle to help you remember how to get to it. 

We recommend AGAINST using complex passphrases like 1 char 1 upper case 1 lower case: refer to https://xkcd.com/936/ to understand why. 

Even using 4-6 words as a passphrase is great, but if doing so ensure to use a technique like Memory Palce and train actively to commit it to memory. Additionally, give your self a hint. Write a poem or a story. Be creative!

### Memory Techniques

For both remembering SeedWords and Passphrases, the Memory Palace technique is surprisingly effective. 

It works on the concept that context is greater than content. If we build a context around our SeedWords or Passphrase, it becomes surprisingly easy to commit it to memory. Once a context is built, repetition is key. Meditate on it every morning for atleast a week and you are set! Imagine yourself walking through your Memory Palace and carving your SeedWords into the walls!

