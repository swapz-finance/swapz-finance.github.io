# Introduction
## About SWAPZ Cryptocurrency Payment
SWAPZ Cryptocurrency Payment System provides a cross-platform payment solution with cryptocurrencies. This document guides you through the functionalities of SWAPZ Cryptocurrency Payment System.

## Pre-requisite of DAPP Integration
Please follow the guidelines below before integration.
- Users are required [create a DAPP on SWAPZ](#steps-to-create-a-dapp) with all the [informations required](#information-required-for-dapp-integration). 
- Users need to generate set of Public & Private Keys by using ED25519 algorithm.
- Create your DAPP on SWAPZ to receive `dappApiKey` and `SWAPZ API Public Key`.

## Information Required to create a DAPP
<table>
<tr><th>Parameter</th><th>Sample</th><th>Description</th></tr>
<tbody>
<tr><td>DAPP Name</td><td>Super Web</td><td>Name of DAPP</td></tr>
<tr><td>Domain/Website</td><td>https://superweb.com</td><td>URL of DAPP's website. It will be used to verify the Response URL and Backend URL during integration. Please take note that do not leave a traling '/'.</td></tr>
<!-- <tr><td>Logo</td><td>-</td><td>Logo of DAPP</td></tr> -->
<tr><td>Dapp Public Key</td><td>-</td><td>Generated with ED25519 algorithm. It is used to verify the signature returned from SWAPZ.</td></tr>
<tbody>
</table>

## Steps to create a DAPP
Go to https://swapz.finance (Production) or https://staging.swapz.finance (Staging). Please log in to your account. If you do not have any SWAPZ's account, feel free to register one.

1. Click on **My DAPP** on the menu.
2. Click **CREATE YOUR DAPP** button to create a DAPP.
<img src="./assets/createDapp1.png" alt="createDapp1">
3. Enter your DAPP Name & Official website then click **CREATE** button. Please take note that these data will display on customer payment page.
<img src="./assets/createDapp2.png" alt="createDapp2">
4. Click **+** button under **Your DAPP API Keys** section to create API key.
<img src="./assets/createDapp3.png" alt="createDapp3">
5. Enter Name and DAPP Public Key, then click **CONFIRM** button. Take note that name is only for your own reference while  DAPP Public Key is the public key you generated in [Pre-requisite of DAPP Integration](#pre-requisite-of-dapp-integration)
<img src="./assets/createDapp4.png" alt="createDapp4">
6. Finally, you can retrive your `dappApiKey` & API Public Key from the list.
<img src="./assets/createDapp5.png" alt="createDapp5">
8. You may create more than one DAPP API Keys by repeating Step 4 to 5.

## Transaction Flowchart
<img src="./assets/transactionFlowchart.svg" alt="transaction flow chart">

## Transaction Processing Step
1. Customer chooses to pay with SWAPZ.
2. DAPP generate all the payment details and signature with the Private Key saved previously in [Pre-requisite of DAPP Integration](#pre-requisite-of-dapp-integration).
3. DAPP sends HTTPS POST Request (Payment Request URL) containing payment details (parameters) and signature to SWAPZ.
4. SWAPZ perform verification and redirect Customer to SWAPZ's payment page.
5. Customer required to login to SWAPZ account for the payment.
6. Customer confirms the payment.
7. Customer views the payment status & details.
8. SWAPZ returns the payment status to DAPP by sending HTTPS POST Request (Response URL) with the payment details (parameters) including a signature.
9. DAPP verify the response's signature and update the payment status wherever are required in DAPP system.
10. Lastly, redirect the customer to a designated page.

** Note: If the customer cancels the payment at step 6, the remaining steps still are proceeded with a status of payment failed.

## Rule, Limitation and Constraint
- Service Hours: 7x24 exclude host down time


