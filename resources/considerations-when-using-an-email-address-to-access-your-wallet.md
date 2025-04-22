---
description: Security warnings
---

# Considerations when using an email address to access your wallet

**Security tips when using an email to access your wallet.**

When a user signs up through our platform using an email address, Web3Auth is used to generate and manage their cryptographic wallet keys. Although it may appear that the wallet is tied directly to the email address, Web3Auth actually creates the wallet based on a unique identity token provided by the user's email service provider.

#### Identity and Key Generation

Web3Auth does not derive the wallet key directly from the email string (e.g., user@example.com). Instead, it initiates an OAuth-based authentication with the provider (such as Google or Microsoft), which responds with a unique internal identifier: a secure, provider-specific value that represents the authenticated account.

This identifier acts as the foundation for generating the user’s private key and, ultimately, their blockchain wallet address. Importantly, this identifier is specific to the exact instance of the user’s account with the provider.

#### What Happens When the Email Account Is Lost and Recreated?

If a user loses access to their original email account and then later recreates an account using the same email address, the email provider will issue a different internal identifier for this new account. Even though the email string looks identical, Web3Auth receives a new identity fingerprint from the provider and therefore generates a completely different cryptographic key and wallet address.

* Web3Auth ties wallet generation to the verified identity behind an email, not the email string itself.\
  \

* A recreated email account results in a different identity being presented to Web3Auth.\
  \

* This leads to the creation of a new wallet address, unrelated to the original.\


This system is designed to ensure that only users with verified, continuous access to their original account credentials can access the corresponding wallet. While this enhances security, it also means that recreating an email account will not restore access to a previously generated wallet.

Thus, when using a email, ideally both you want to both use Multi-factor authorization to your wallet, and make sure you and only you have access to your wallet. Be very careful when deleting an email address, as wallets connected to it could be lost unless MFA is set up

By following these best practices, you’ll ensure that your Alberto Wallet remains secure and that you can manage your digital assets with confidence.
