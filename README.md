## Rascunho

### Segurança de sistemas
#### Autenticação
##### Secret Zero Problem
[The Secret Zero Problem](https://developer.cyberark.com/blog/secret-zero-eliminating-the-ultimate-secret/#:~:text=The%20Secret%20Zero%20Problem,master%20key%20that%20unlocks%20everything.)

No que consiste o problema: Dado um conjunto de senhas e segredos, estes estão protegidos por uma única senha.
Um exemplo disso é o conjunto de senhas estar armazenado num arquivo de texto, e o acesso a esse arquivo se dá por uma única senha.

"It is a lot like putting all your eggs in one basket or locking all of your keys in drawer and then putting that key in your pocket. Yhe job is not done after securing your secrets, you alson need to secure access to your secrets."

"Access control, secrets management, and identity are all dependent on each other. Managing secrets at scale requires effective access control; implementing access control requires identity; proving identity requires possession of a secret. **Protecting one secret requires coming up with some way to protect another secret, which then requires protecting that secret, and so on.**" 
([Solving the bottom turtle](https://spiffe.io/pdf/Solving-the-bottom-turtle-SPIFFE-SPIRE-Book.pdf))

#### Notas & Destaques do livro Solving The Bottom Turtle

##### Adopting Public Cloud
"The ability to provision and deprovision resouces on-demand enabled high-velocity creation of suites of specialized, focused, and independently deployable services with a *smaller scope of responsability*, colloquially referred to as microservices."

This highly dynamic and elastic environment broke accepted perimeter security concepts.
Conventional boundary enforcement used IPs and ports for authentication, authorization, and auditability, which unde cloud computing paradigms no onger cleanly mapped workloads.
--> The need for identities not dependent on network topology or path

New technologies: containers, microservices, cloud computing, serverless functions; there are smaller pieces of software

##### Re-imagining Access Control
"Deperimeterization meant that organizations needed to figure out how to identify their software and enable service-to-service access control"

How should workloads get access to this secret repository? 
Turtles all the way down

"As organizations have moved to cloud computing with rapid deployment pipelines and automatically scaled resources, it becomes infeasible to manually provision secrets as new compute units are created. And whe secret *is* compromised, invalidating the old credential can pose risk of bringing down the entire system."

**There must be a root of trust, upon which an automated solution centered around software (workload) identity is built**

(?)
- Solve secret zero problem by leveraging kernel-based introspection to obtain information about the caller without the caller having to preent a credential
- Effectively divorcing the concept of identity from network locators

"The initial goals of solving the workload identity problem were to establish an open specification and corresponding production implementation. The framewrk needed to provide interoperability between different implementations and off-the-shelf software, at its core establishing a root of trust in an untrusted environment, **exocising implicit trust**. And finally, moving away from network-centric identity to achieve flexibility and better scaling properties"

Soluções possíveis existentes:
- Hashicorp Vault
- SPIFFE/SPIRE

##### SPIFFE/SPIRE Benefits
- Standardizing how systems define, attest, and maintain software security identity, regardless of where systems are deployed or who deploy those systems

##### Identity in the Digital World: Cryptographic Identities
- **X.509 certificates**
	- Key weakness: any CA can sign any certificate, with no restrictions
	- It is vital that each well-known CA is completely trustworthy, and that each intermediate CA they delegate to is also completely trustworthy
- Signed JSON Web Tokens
- Kerberos tickets
- **Public Key Infrastructure**
	- A set of roles, policies, hardware, software, and procedures needed to create, manage, distribute, use, store and revoke digital cerificates and manage publickey encryption

- The longer a certificate is valid, the greater the risk tha the private key for its certificate or any certifcate leading to the root could be stolen

- Authentication: "The most common use of an identity document is as a basis for authentication"

#### Zero Trust Architecture
[Ler artigo](https://csrc.nist.gov/publications/detail/sp/800-207/final)


