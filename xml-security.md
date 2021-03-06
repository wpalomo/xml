# XMLSecurity
A VFP set of classes to secure an XML document (encrypt, signing, and verifying).

Part of [VFP XML library set](README.md "VFP XML library set").

## Credits

- A VFP porting of XMLSecLibs, a PHP library for XML Security by Rob Richards and contributors (at
[https://github.com/robrichards/xmlseclibs](https://github.com/robrichards/xmlseclibs))

## Status

- Not suited for production.
- See tests for current coverage of functionality.

## Usage
See examples at the tests folder:

- [Sign an XML document - basic](tests/sec/test-hw-sign.prg "test-hw-sign.prg")
- [Verify the signature in a signed XML document](tests/sec/test-hw-verify.prg "test-hw-verify.prg") (uses the output from the precedent test)
- [Verify the signature in a signed XML document](tests/sec/test-getfile-verify.prg "test-getfile-verify.prg") (uses an externally signed document - KeyValueInfo limited to X509Certificate and RSAKeyValue, for now)
- [Sign an XML element](tests/sec/test-hw-child-sign.prg "test-hw-child-sign.prg")
- [Sign an XML element with its own Id](tests/sec/test-hw-child-id-sign.prg "test-hw-child-id-sign.prg")
- [Sign an XML document and put it inside an enveloping signature](tests/sec/test-hw-sign-enveloping.prg "test-hw-sign-enveloping.prg")
- [Sign a text and put it inside an enveloping signature](tests/sec/test-text-sign-enveloping.prg "test-text-sign-enveloping.prg")
- [Encrypt an XML document](tests/sec/test-hw-encrypt.prg "tests/sec/test-hw-encrypt.prg")
- [Decrypt an encrypted XML document](tests/sec/test-hw-decrypt.prg "tests/sec/test-hw-decrypt.prg") (uses the output from the precedent test)
- [Encrypt the content of an XML node](tests/sec/test-hw-content-encrypt.prg "tests/sec/test-hw-content-encrypt.prg")
- [Decrypt the content of an encrypted XML node](tests/sec/test-hw-content-decrypt.prg "tests/sec/test-hw-content-decrypt.prg") (uses the output from the precedent test)
- [Encrypt the text content of an XML node](tests/sec/test-hw-text-content-encrypt.prg "tests/sec/test-hw-text-content-encrypt.prg")
- [Decrypt the text content of an encrypted XML node](tests/sec/test-hw-text-content-decrypt.prg "tests/sec/test-hw-text-content-decrypt.prg") (uses the output from the precedent test)
- [Encrypt an XML document using a symmetric key](tests/sec/test-hw-encrypt-symmetric.prg "tests/sec/test-hw-encrypt-symmetric.prg")
- [Decrypt an XML document using a symmetric key](tests/sec/test-hw-decrypt-symmetric.prg "tests/sec/test-hw-decrypt-symmetric.prg") (uses the output from the precedent test)

## Components

- [XMLSecurity header file](xml-security.h "xml-security.h")
- [XMLSecurityLib, a class to perform encryption and hashing operations](xml-security-lib.prg "xml-security-lib.prg")
- [XMLSecurityLibChilkat, an XMLSecurityLib subclass that interfaces to Chilkat RSA, Crypt2, and Cert components](xml-security-lib-chilkat.prg "xml-security-lib-chilkat.prg")
- [XMLSecurityLibOpenSSL, an XMLSecurityLib subclass that interfaces to OpenSSL's libcrypto.dll](xml-security-lib-openssl.prg "xml-security-lib-openssl.prg")
- [XMLSecurityKey, a class to manage key related operations](xml-security-key.prg "xml-security-key.prg")
- [XMLSecurityDSig, a class to sign XML documents and fragments](xml-security-dsig.prg "xml-security-dsig.prg")
- [XMLSecurityEnc, a class to encrypt XML data)](xml-security-enc.prg "xml-security-enc.prg")

## Dependencies

- [XMLCanonicalizer](xml-canonicalizer.md "XMLCanonicalizer")
- [GUID](https://www.bitbucket.org/atlopes/GUID "GUID")
- [URL](https://www.bitbucket.org/atlopes/url "URL")

Additionally, XMLSecurity requires a crypto library to provide the encryption and hashing functions. The distributed XMLSecurityLib sub-classes provide interfaces to two such components, 
[OpenSSL](https://www.openssl.org "OpenSSL"), a widely used open source solution, and 
[Chilkat](https://www.chilkatsoft.com/refdoc/activex.asp "Chilkat"), a commercial product that adds significant value to a VFP development environment.

To use the OpenSSL library, at least `libcrypto.dll` must be present in VFP's path, but a full OpenSSL package may be installed from one of the available sources listed in the project wiki: 
[https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries). 


