# Task 5 - Masquerade

## Prompt

The app uses a bespoke application of the OAUTH protocol to authorize and authenticate TerrorTime users to the chat service. Our intelligence indicates that individual terrorists are provided phones with TerrorTime installed and pre-registered to them. They simply need to enter their username and secret PIN to access the chat service, which uses OAUTH behind the scenes to generate a unique token that is used for authentication. This is a non-standard way of using the protocol, but they believe it to be superior to normal password-based authentication since a unique token is used per login vs. a static password. Whether that is indeed the case is up to you to analyze and assess for possible vulnerabilities. Our forensics team recovered a deleted file from the terrorist's hard drive that may aid in your analysis.

Through other intelligence means, we know that the arrested terrorist is a member of one of many cells in a larger organization. He has shown no signs of someone who is acting in a leadership role -- he simply carries out orders given to him from his cell leader, who is likely relaying information from the top-level organizational leader. To uncover information from the cell leader’s conversations, we need access to their account. The messages are end-to-end encrypted, so without the leader's private key we won't be able to decrypt his messages, but we may be able to learn more about the members of the cell and the organization's structure. Analyze the client and server-side components of the authentication process and find a way to masquerade as arbitrary users without knowing their credentials. Take advantage of this vulnerability and masquerade as the cell leader. Access and review the cell leader’s relevant information stored on the server. Use this information to identify and submit the top-level organizational leader’s username and go a step first and submit a copy of the last (still encrypted) message in the organization leader’s chat history. It’s suggested to complete task 4 before attempting this task as task 4 aids in discovering the cell leader’s identity.

## Provided Files

* `auth_verify.pyc`

## Solution

### OAUTH Exploitation

Any token can be used to get encrypted chats if you use their ID, but a different ID to retrieve token.
Use burp to use Jason's creds for Aden's key and try all names as cell leader


### XMPP Intercept

Set XMPP server IP to a MITM relay on my machine and then log in as aden to see encrypted messages.