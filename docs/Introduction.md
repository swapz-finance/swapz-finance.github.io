# Introduction
## About SWAPZ Cryptocurrency Payment
SWAPZ Cryptocurrency Payment System provides a cross-platform payment solution with cryptocurrencies. This document guides you through the functionalities of SWAPZ Cryptocurrency Payment System.

## Pre-requisite of DAPP Integration
Please follow the guidelines below before integration.
- Users are required to apply for DAPP integration with all the [informations required](#information-required-for-dapp-integration). 
- Users need to generate set of Public & Private Keys by using ED25519 algorithm.
- Users are required to save the Public & Private Keys.
- Submit the application for DAPP integration and attach the Public Keys accordingly.
- The `dappApiKey` and `SWAPZ API Public Key` will then be issued to the applicant.

## Information Required for DAPP Integration
<table>
<tr><th>Parameter</th><th>Sample</th><th>Description</th></tr>
<tbody>
<tr><td>DAPP Name</td><td>Super Web</td><td>Name of DAPP</td></tr>
<tr><td>Domain/Website</td><td>https://superweb.com</td><td>URL of DAPP's website. It will be used to verify the Response URL and Backend URL during integration.</td></tr>
<tr><td>Logo</td><td>-</td><td>Logo of DAPP</td></tr>
<tr><td>Dapp Public Key</td><td>-</td><td>Generated with ED25519 algorithm. It is used to verify the signature returned from SWAPZ.</td></tr>
<tbody>
</table>

## Transaction Flowchart
<img src="./assets/transactionFlowchart.svg" alt="">

## Transaction Processing Step
1. Customer chooses to pay with SWAPZ.
2. DAPP generate all the payment details and signature with the Private Key saved previously during the [application of DAPP integration](#pre-requisite-of-dapp-integration).
3. DAPP sends HTTPS POST Request (Payment Request URL) containing payment details (parameters) and signature to SWAPZ.
4. SWAPZ perform verification and redirect Customer to SWAPZ's payment page.
5. Customer required to login to SWAPZ account for the payment.
6. Customer confirms the payment.
7. Customer views the payment status & details.
8. SWAPZ returns the payment status to DAPP by sending HTTPS POST Request (Response URL) with the payment details (parameters) including a signature.
9. DAPP verify the response's signature and update the payment status wherever are required in DAPP system.
10. Lastly, redirect the customer to a designated page.

** Note: If customer cancels the payment at step 4, the remaining steps still go on with a payment failed status.
## Rule, Limitation and Constraint
- Service Hours: 7x24 exclude host down time


