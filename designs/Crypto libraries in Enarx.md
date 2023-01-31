# Crypto libraries in Enarx

###### tags: `Design`

## Crypto Libraries
1. Ring - BoringSSL
2. Rust Crypto - Pure Rust


## HTTPS libraries
1. Rustls - Uses Ring


## Where used
1. Rustls - Drawbridge interaction
2. Rustls - TLS connections in/out of the Keep
3. Rust Crypto - generating CSR for Steward, or self-signed cert