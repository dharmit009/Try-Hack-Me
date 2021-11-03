# What is RSA ?

RSA stands for Rivest Shamir Adleman. The RSA is based is mainly based on finding factors of large number. It’s very quick to multiply two prime numbers together, say 17\*23 = 391, but it’s quite difficult to work out what two prime numbers multiply together to make 14351 (113x127 for reference).

## Things you need to remember.

The key variables in RSA are p,q,m,n,e,d, and c. 

p -> are large prime numbers.  
q -> are large prime numbers. 
m -> It is used to message (in plaintext).
n -> is a product of p\*q
e -> n * e is public key.
d -> n * d is private key.
c -> represent cipher text. 


## Answer the questions below

p = 4391, q = 6659. What is n?
> 29239669

### Resources 

1. https://muirlandoracle.co.uk/2020/01/29/rsa-encryption/
1. https://github.com/Ganapati/RsaCtfTool
1. https://github.com/ius/rsatool
