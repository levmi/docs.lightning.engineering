---
description: >-
  Lightning Service Authentication Tokens cleverly combine the capabilities of
  macaroons with that of a Lightning payment, making it easy to charge satoshis
  for API requests.
---

# LSAT

In this document, we outline the design for a Lightning Service Authentication Token \(LSAT\) for future services created by [Lightning Labs](https://lightning.engineering/). This specification is open source, with contributions accepted at our [LSAT specification repository](https://github.com/lightninglabs/LSAT). LSATs are a new standard protocol for authentication and paid APIs developed by Lightning Labs. LSATs can serve both as authentication, as well as a payment mechanism \(one can view it as a ticket\) for paid APIs. In order to obtain a token, we require the user to pay us over Lightning in order to obtain a pre-image, which itself is a cryptographic component of the final LSAT token.

The implementation of the authentication token is chosen to be macaroons, as they allow us to package attributes and capabilities along with the token. This system allows us to automate pricing on the fly and allows for a number of novel constructs such as automated tier upgrades. In another light, this can be viewed as a global HTTP 402 reverse proxy at the load balancing level for all our services.

{% page-ref page="introduction.md" %}

{% page-ref page="authentication-flow.md" %}

{% page-ref page="protocol-specification.md" %}

{% page-ref page="macaroons.md" %}

## Implementations <a id="implementations"></a>

* ​[Aperture: A gRPC/HTTP authentication reverse proxy using LSATs](https://github.com/lightninglabs/aperture)​
* ​[lsat-js: A utility library for working with LSATs](https://github.com/Tierion/lsat-js)​
* ​[boltwall: Nodejs middleware-based authentication using LSATs](https://github.com/tierion/boltwall)​

## External links / References <a id="external-links-references"></a>

* ​[LSAT: Your Ticket Aboard the Internet's Money Rails](https://docs.google.com/presentation/d/1QSm8tQs35-ZGf7a7a2pvFlSduH3mzvMgQaf-06Jjaow/edit#slide=id.p)​

  slides to Olaoluwa Osuntokun's \(@roasbeef\) presentation at The Lightning Conference 2019 in Berlin.

* ​[LSAT Playground](https://lsat-playground.bucko.now.sh/)​
* ​[Macaroons: Cookies with Contextual Caveats](https://research.google/pubs/pub41892/)​

  the 2014 paper published on Google Scholar.

* ​[HTTP/1.1 RFC, Section 6.5.2: 402 Payment Required](https://tools.ietf.org/html/rfc7231#section-6.5.2)​
* ​[Proposal for OAuth style delegated authentication using LSATs](https://github.com/lightningnetwork/lnd/issues/288)

