## Rascunho

### Segurança de sistemas
#### Autenticação
##### Secret Zero Problem
[The Secret Zero Problem](https://developer.cyberark.com/blog/secret-zero-eliminating-the-ultimate-secret/#:~:text=The%20Secret%20Zero%20Problem,master%20key%20that%20unlocks%20everything.)

No que consiste o problema: Dado um conjunto de senhas e segredos, estes estão protegidos por uma única senha.
Um exemplo disso é o conjunto de senhas estar armazenado num arquivo de texto, e o acesso a esse arquivo se dá por uma única senha.

"It is a lot like putting all your eggs in one basket or locking all of your keys in drawer and then putting that key in your pocket. Yhe job is not done after securing your secrets, you alson need to secure access to your secrets."

"Access control, secrets management, and identity are all dependent on each other. Managing secrets at scale requires effective access control; implementing access control requires identity; proving identity requires possession of a secret. *Protecting one secret requires coming up with some way to protect anothe secret, which then requires protecting that secret, and so on.*" 
([Solving the bottom turtle](https://spiffe.io/pdf/Solving-the-bottom-turtle-SPIFFE-SPIRE-Book.pdf))
