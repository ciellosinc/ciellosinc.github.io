# Links

[Sign an APP Package File](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-sign-extension)

[Code Signing Certificates Product Comparison | DigiCert](https://www.digicert.com/signing/compare-code-signing-certificates)


# [Introduction to Code Signing](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))

One of the larger questions facing the software industry is this: How can users trust code that is published on the Internet?
Packaged software uses branding and trusted sales outlets to assure users of its integrity, but these are not available when code is transmitted on the Internet. Additionally, there is no guarantee that the code hasn't been altered while being downloaded. Browsers typically exhibit a warning message explaining the possible dangers of downloading data, but do nothing to actually see whether the code is what it claims to be. A more active approach must be taken to make the Internet a reliable medium for distributing software. 

One of this approach is **Digital Certification**.

## [Digital Certificates](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85)#digital-certificates)

> A certificate is a set of data that completely identifies an entity, and is issued by a certification authority only after that authority  has verified the entity's identity. The data set includes the entity's public cryptographic key. When the sender of a message signs the message with its private key, the recipient of the message can use the sender's public key (retrieved from the certificate either sent with the message or possibly available elsewhere in the directory service) to verify the sender's identity.

## [Certificate Store Technology](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85)#certificate-store-technology)

In order to perform a code signing operation, both private key and signer identification information must be supplied. The digital certificate used in the signature usually supplies the signer identification information, however. Thus, the private key must be supplied through some other means. Additionally, the signature must include the certificate chain for the cryptographic service provider (CSP), up to a root certificate trusted by the user, in order for the signed file to be authenticated. So in all, there are several items that need to be provided in order to generate a digital signature.

Microsoft has developed a certificate store technology to reduce the above complexity. Using this technology, when a user enrolls to obtain a certificate, they specify the private key information, the CSP information, and the certificate store name for the certificate. The certificate will then be stored in the certificate store and be associated with the other items. When the user wants to sign a document, they only need to identify the certificate in the certificate store. The code signing tool will retrieve the certificate, the private key, and the certificate chain for the CSP, all based on the specified certificate.

**Using Microsoft's certificate store technology, only one certificate is necessary to perform a digital code signing operation. This relieves users from having to manage private key and CSP information.
**

## [Digital Certification](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85)#digital-certification)


One of the primary goals of a digital certificate is to confirm that the public key contained in a certificate is, in fact, the public key belonging to the person or entity to whom the certificate is issued.


::: mermaid
sequenceDiagram 
    Sender->>Certification Authority: Request with name and public key
    Certification Authority->>Certification Authority: creates a special message (m) from request
    Certification Authority->>Certification Authority: signs the message with its private key
    Certification Authority->>Sender: returns the message m and the signature sig
    Sender->>Sender: returns the message m and the signature sig
    
    Note right of Certification Authority: Rational thoughts!
    loop Healthcheck
        John->>John: Fight against hypochondria
        John-->>Alice: Great!
    end
    Note right of John: Rational thoughts!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
:::

Code signing is the process of digitally signing a file to verify the author and that the file hasn't been tampered with since it was signed.
