# Crypto Dating and the DATE token


## 1 Introduction
Crypto Dating is an attempt to address some of the problems with relationship matching using technology and ideas related to the blockchain. 
While we will propose a specific implementation, theoretically this can also be viewed as a protocol, or template, for apps to follow.

### 1.1 Vision
Fixing the idea of dating seems truly an ambitious undertaking. Who can even put an accurate time on the origin of dating? Dating, and courtship before that, can be traced back to about the 1700's (before which marriages were most often arranged). Modern dating, for which we will fix a date to the latter half of the 20th century untill today, has one simple problem... honesty. People inherintely do not want to hurt other peoples feelings. But in doing so may actually cause more harm (and to themselves as well). So to solve this problem we present the DATE token and the priciples of using ideas from blockchain and cryptographic / trustless systems to help root out the misplaced feelings and help people move on more quickly to find love.

### 1.2 Background
Anyone who has attemped online or app dating (and even general dating before that) understands the a person's true feelings can often times be at odds with their unwillingess to be honest.
For example, John may really like Betty, but Betty might just not be into John. Since John is a nice guy she talks to him for a while and drags it out, but ultimately their relationship fails to progress.
Both sides can agree, honesty is the best result here. Even if John will be heartbroken because he thinks he found his soulmate, if he can find out sooner instead of wasting so much time, it will prove better for him.
But most people inheritenly hate to see some else discomforted by something they have done, and thus we face this issue where we subsitute honesty for 'kindness'.
The solution to this problem is rooted in lessons from Bitcoin, blockchain, decentralization, and trustless systems.

### 1.3 Terminology
__Blockchain:__ a system in which a record of transactions made in bitcoin or another cryptocurrency are maintained across several computers that are linked in a peer-to-peer network.

__Chain:__ short for Blockchain, see above definition.

__Collateral:__ something pledged as security for repayment of a loan, to be forfeited in the event of a default.

__Escrow:__ a bond, deed, or other document kept in the custody of a third party and taking effect only when a specified condition has been fulfilled.

__Non Fungible Token:__ a special type of cryptographic token which represents something unique; non-fungible tokens are thus not interchangeable. This is in contrast to cryptocurrencies like bitcoin, and many network or utility tokens that are fungible in nature.[1]

__Token:__ a voucher that can be exchanged for goods or services, typically one given as a gift or offered as part of a promotional offer.

__Wallet:__ A cryptocurrency wallet is a device, physical medium, program or a service which stores the public and/or private keys and can be used to track ownership, receive or spend cryptocurrencies.[2]


## 2 Hash Locked Escrow Contracts (dating contracts)

### 2.1 What are Hash Locks
>A Hashlock is a type of encumbrance that restricts the spending of an output until a specified piece of data is publicly revealed. Hashlocks have the useful property that once any hashlock is opened publicly, any other hashlock secured using the same key can also be opened. This makes it possible to create multiple outputs that are all encumbered by the same hashlock and which all become spendable at the same time. Hashlocks have been used independently (see below) but are most commonly described as part of a system such as Hashed Timelock Contracts.[3]

Fortunately, hashlocks provide a sort of template for what we are trying to achieve in the 'Dating Contract'. Ultimately, we want a contract between to parties that says: 'I, person A, want to go out with you. I am willing to escrow DATE tokens to prove I am sincere.' Now person B has a choice to make. In the days of old, person B might just say 'Yeah, I think you're swell. We should definitely go out.' But now B must actually prove their sincerity. So if B want's to go on the date, B must also post DATE tokens as collateral. The act of posting this collateral effects a digital signature that is posted to the blockchain. If for any reason, A or B does not go on the date, they will forfeit their escrow and the other party effictively gets compensated financially for being stood up. Now of course A might be heartbroken still and to be sure a escrow forfeiture from B will not mend that, but it does provide a stronger base for A to make future dating decisions. Therefore, someone who get's 'stood up' a few times will have additional DATE tokens in their wallet for use however he/she deems fit.

## 3 

## 4 Accounts

### 4.1 Initial token grant
Upon signing up for an account on the app, each user will be granted an 'Initial token grant'. This grant will be free of charge for the user and represent enough token value for the posting of one date's worth of escrow.

### 4.2 Additional purchases
User's may replenish their token balance at any point by purchasing additional tokens with fiat currency at a fixed exchange rate to USD or by converting crypto currency at a floating exchange rate based on dynamic inputs.

### 4.3 Wallets
Each user will initialize a wallet (transparent to them) upon the activation of their account on the platform. The wallet will be a captive wallet, similar to Brave Browser's wallet implementation, which does not require any specific action by the user other than an optional backup. From this backup the user can theoretically run their wallet off of the application's platform, but will provide limited or no ability to use the token for the stated objective of date escrow collateral.


## 5 Token

### 5.1 Paying for dating
Users may be reluctent to spend actual money for use within a dating app. This is partly because many services offer a free matching platform and offer purchases for 'premium' accounts. The new generation of these have done a better job of appealing to the mass dating market, for example, such as Tinder's premium feature allowing you to see others who have already 'right swiped' you. While swiping through the whole card stack can be fun, it's often more efficient to look and choose amongst the people who have already approved you. As a side note: Tinder and Bumble both offer an asymmetric card stack whereby you can set your age parameter to say 20 - 50, and you will see cards for that range. However that does not mean that everyone in the 20 - 50 range will be presented with _your_ card when swiping. Because of this mismatch it is also more efficient to purchase a premium account, eliminating the guess work about who may have had you in _their_ range. More legacy dating apps relied on either a model whereby which browsing was free but contacting a user would cost some money. Or in-app purchases such as 'virtual flowers'. For younger generations, these virtual flowers (et all) are rarely viewed as grand gestures and can even have a negative impact. ***CITATION NEEDED***

### 5.2 Uses within the app
The DATE token solves the collateral issue for us, but also can address the problem(s) above. For instance, as virtual gifts, instead of flowers, one user can present to another user a NFT.

### 5.3 Limitation of token redemption
There is no planned market for the redemption of tokens. While users may acquire tokens through escrow forfeitures by the other party, they will only be used in app. One possible redemption method would be additional in app purchases using these tokens beyond the standard posting of escrow collateral. It is also feasible that, given tokens have a fixed monetary value, that a secondary market would develop for both fiat currencies and also other crypto assets.



[0] History of Dating: https://en.wikipedia.org/wiki/Dating

[1] Non fungible Token: https://en.wikipedia.org/wiki/Non-fungible_token

[2] Wallet Definition: https://en.wikipedia.org/wiki/Cryptocurrency_wallet

[3] Hashlocks: https://en.bitcoin.it/wiki/Hashlock