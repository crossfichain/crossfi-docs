# XDS

XDS is a decentralized domain name system designed to enhance user interaction with the CrossFi blockchain ecosystem.

## Key Features

**Simplified Interaction**

The system replaces complex crypto addresses with easy-to-remember names in the format `username.xds`. This significantly reduces the risk of errors when sending transactions and makes blockchain interactions more intuitive.

**Decentralized Web**

Users can link their XDS names to content on IPFS, creating decentralized websites. It is also possible to associate domain names with various profiles and contact details.

**Integration with DApps**

The system allows readable names to be used instead of addresses when working with decentralized applications, improving convenience and security in interactions.

***

## How XDS Works

XDS is built on three key components: the registry, registrars, and resolvers.

#### Registry: The Core Storage

The registry is a smart contract on the Ethereum network that stores all domain names (keys) and their associated data (values). It records the domain owner's address and a pointer to the resolver. Owners can transfer ownership, update records, and change the resolver via blockchain transactions.

#### Registrars: Registration Rules and Mechanisms

Registrars define the conditions for obtaining and renewing domain names (e.g., in the ".xds" zone). Most names are registered directly, but premium names may require an auction. Registrars also track registration periods and send renewal reminders to prevent domain loss.

#### Resolvers: Name Resolution

Resolvers convert XDS names (e.g., `ivan.xds`) into necessary addresses: Ethereum, IPFS hashes, or other data. Owners specify which resolver to use to link their domain to a particular resource. Resolvers support various record types, from cryptocurrency addresses to text data.

***

## Name Registration Process

Registering a name in XDS involves several steps to ensure secure and convenient domain usage.

{% stepper %}
{% step %}
#### Checking Name Availability

Users check the availability of their desired name through the XDS web interface or other compatible services.
{% endstep %}

{% step %}
#### Auction or Direct Registration

Most names are available for direct registration. Premium names may require participation in an auction.
{% endstep %}

{% step %}
#### Choosing Registration Period and Payment

* **Registration Period:** From one year to an unlimited period.
* **Payment:** Made in ETH via a compatible wallet.
{% endstep %}

{% step %}
#### Confirming Registration and Setting Up a Resolver

After payment, registration is confirmed on the Ethereum network. The owner can configure the resolver to link the domain name to a specific Ethereum address or other records.
{% endstep %}

{% step %}
#### Updating and Renewing

Owners can update their records or change resolvers. To avoid expiration, names must be renewed periodically.
{% endstep %}
{% endstepper %}

***

## XDS Use Cases

#### Simplified Transactions

Instead of a long address, users can send funds to `ivan.xds`, reducing the risk of entering an incorrect wallet address. This is especially useful for frequent transfers without manually verifying long address strings.

#### Decentralized Websites and Identification

XDS names simplify content hosting on IPFS: instead of an IPFS hash, a domain name is used. Users can also link their social profiles, email, and other contact details, making identification in a decentralized environment easier.

#### Interaction with DApps

DApps can accept XDS names alongside Ethereum addresses, streamlining authentication and increasing platform trust by displaying verified names instead of unreadable hex addresses.

#### Name Resolution

XDS automatically converts names into various formats: Ethereum addresses, IPFS hashes, text records, etc. This enables a single domain name to serve multiple purposes—from sending tokens to accessing decentralized websites.

***

## Integrating XDS into a Project

#### Storage and Caching

To avoid frequent registry queries, projects with high request volumes can cache resolution results. This optimizes name handling and speeds up application response times.

#### Smart Contract Updates

To support XDS names within existing logic (e.g., payment processing or custom records), smart contracts need to be adapted for registry and resolver interactions. This requires analyzing current architecture and potential modifications.

#### User Interface

Input fields and automatic XDS name resolution should be implemented to allow users to enter readable names instead of long addresses. Validation and user-friendly error messages should be provided to assist with incorrect input or network issues.

#### Tools and Libraries

Developers can use **Ethers.js** (which includes built-in resolution methods) or **Web3.js** (via low-level smart contract calls) to efficiently integrate XDS into projects of any scale.

***

## User Interaction

#### Name Input and Resolution

Users enter an XDS name, and the application retrieves the associated address or other information in the background. This eliminates the need to manually copy and paste long character sequences.

#### Domain Management Interface

Registering a new name involves entering the desired domain, selecting the validity period, and paying in ETH. Owners can later renew registrations, change resolvers, and transfer domains to other accounts if needed.

#### Profile Association

Applications can display XDS names instead of Ethereum addresses, improving usability and clarity. Users can link their domains to accounts or wallets for quick identification.

***

## Practical Examples and Use Cases

* **Uniswap:** Allows sending tokens to XDS names, improving UX and reducing error risks.
* **Etherscan:** Displays transaction results in a human-readable format, making searches and analysis easier.
* **Argent:** Assigns a unique XDS name to each user when creating a wallet, simplifying transfers and recognition.
* **OpXDSea:** Shows XDS names when buying or selling NFTs, increasing transparency in transactions.
* **Alchemy:** Simplifies blockchain app development and testing by using easily memorable names instead of addresses.
