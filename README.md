This package provides Rust bindings for the functionality exposed by OpenSSL's
libcrypto. Currently provided:

* Hashes (hash.rs)
  * MD5
  * SHA-1
  * SHA-2 (224, 256, 384, 512)
* Symmetric crypto (symm.rs)
  * AES in ECB or CBC mode, all key lengths
* Keypair generation (pkey.rs)
  * RSA, all key lengths
* Asymmetric encryption (pkey.rs)
  * RSA with PKCS#1 OAEP padding
* Digital signatures (pkey.rs)
  * RSA with whatever your system openssl does (PKCS#1 on my system) and sha256

Each module provides two interfaces: a low-level API which wraps the OpenSSL
interfaces as directly as possible and a high-level API which presents the
OpenSSL API as a Rust object and tries to make sensible default choices about
parameters most users won't care about. You probably want to use the high-level
API. For documentation on these, see the individual source files.
