# User Guide - Secure Connection to the TIN Validation API

TIN Validation System - CRS-CIAT

> This guide is intended for authorized users only (machine-to-machine applications).

## Overview

The TIN validation API at **https://ciat.org/validatin** uses a secure authentication method based on OAuth 2.0 with `private_key_jwt` (RFC 7523).

This means no shared passwords are used. Instead, your application generates a cryptographic key pair (private and public) and uses the private key to sign a token request to the IAM (**https://ciat.org/iam/auth**).

The IAM verifies the signature using the previously registered public key and, if valid, issues a temporary access token that you use to call the API.

This method is highly secure and recommended for machine-to-machine communication.

## Generate Keys

### Step 1: Generate the Key Pair (One-time only)

You need to create:

- **Private key** (private_key.pem): Keep it secret. Never share it!
- **Public certificate** (public_cert.pem): This is the one you register in the system.

Use **OpenSSL** (free tool available on Windows, Linux, and macOS):

openssl req -x509 -newkey rsa:2048 -keyout private_key.pem -out public_cert.pem -days 365 -nodes

You will be prompted for information (name, organization, country). You can press Enter to leave blank or enter generic data.

**Result:** Two files in the current folder.

## Register Certificate

### Step 2: Register the Public Certificate

Send the contents of the `public_cert.pem` file to the CIAT system administrator or upload it via the client registration portal (if available).

The system will associate this certificate with your **client_id** (a unique identifier provided to you).

Once registered, you can start requesting tokens.

## How Authentication Works

### Step 3: How Authentication Works (Detailed Explanation)

Your application creates a small JWT with basic data (who you are, time, IAM address) and signs it with your private key.

The IAM verifies the signature using the registered public key.

#### Mathematical Process of Signing and Verification (RSA - RS256)

1. A hash (unique summary) of the JWT message is calculated.
2. Using the **private key**, a mathematical operation is applied (raising the hash to a secret power modulo n).
3. Result: the **signature**.
4. The IAM calculates the same hash of the message.
5. It applies the **inverse operation** with the **public key** (raising the signature to a public power modulo n).
6. If the result exactly matches the hash, the signature is valid → irrefutable proof that it was created with the corresponding private key.

It is impossible to forge without the private key due to the extreme mathematical difficulty of factoring large numbers.

## Obtain Token

### Step 4: Obtain the Access Token

We recommend using libraries that automate this process:

- **Python**: Authlib
- **.NET/C#**: MSAL.NET
- **Java**: Nimbus JOSE + JWT

If done manually, send a POST to the endpoint `https://ciat.org/iam/auth` with parameters such as `client_assertion_type=urn:ietf:params:oauth:client-assertion-type:jwt-bearer` and the signed JWT as `client_assertion`.

The IAM responds with an access_token (valid for hours).

## Call API

### Step 5: Call the API

In every request to **https://ciat.org/validatin**, include the header:

Authorization: Bearer <your_access_token>

The API will verify the token with the IAM (or directly if it is a JWT signed by the IAM).

Renew the token when it expires.