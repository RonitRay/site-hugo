+++
title= "Cryptography- A Regret and A Request"
date= 2021-01-22
description= "Musings on rolling your own crypto and my academic misadventures."
[extra]
listed=true
+++

In my second year in university as a CS major, I pitched an academic paper to an IEEE conference along with three colleagues. The paper highlighted a "novel" symmetric encryption scheme that we'd spent the better part of the summer brainstorming. It wasn't without its merits, and seemed to fulfill [the absolute basics of cryptography](https://sites.google.com/site/kryptosgrapheinen/overview/objectives) well enough. We mostly thought of it as a toy project, and went ahead to make an encrypted chat application, where keys were generated on the initiating device and shared to the recipient via an implementation of the [Diffie-Hellman Key Exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange). At the time, everyone involved was rather excited about it, and while we didn't think of ourselves as cryptographic pioneers, having the paper accepted certainly was a matter of pride and added what we felt was some legitimacy to our efforts.

It took some time before my interest in security and privacy led me to realize the issues with what we had cooked up. It was slow, and lacked forward secrecy in any form whatsoever, and that was just the beginning. We hadn't yet come across the tenet that [you don't roll your own crypto.](https://resources.infosecinstitute.com/topic/the-dangers-of-rolling-your-own-encryption/) Toy projects are fine, they're educational and can help you understand a lot of things that lectures might not. But these ideas once cemented, if encouraged unconditionally, legitimized, and not corrected, can lead to any of us deploying their own ham-fisted encryption in a production application, and that can have disastrous consequences.

Quoting [this excellent CryptoFails article](https://www.cryptofails.com/post/75204435608/write-crypto-code-dont-publish-it),

> Donald Rumsfeld said this:

> > _There are known knowns. These are things we know that we know. There are known unknowns. That is to say, there are things that we know we don’t know. But there are also unknown unknowns. These are things that we don’t know we don’t know._

> _I hypothesize that most crypto errors, especially the ones at the design level, are “unknown unknowns” to the designer._

Quoting [another excellent article on why RSA is a bad idea to use as a primary encryption scheme](https://soatok.blog/2021/01/20/please-stop-encrypting-with-rsa-directly/),

> _First, consider not using RSA. Hell, while you’re at it, don’t write any cryptography code that you don’t have to._

> _Libsodium (which you should use) does most of this for you, and can easily be turned into an AKE comparable to the one Signal uses. The less cryptography code you have to write, the less can go catastrophically wrong–especially in production systems._

If you are an educator, a supervisor, a reviewer, please encourage students to think critically about cryptography and devise new cryptosystems for fun, but also remind them that standing on the shoulders of giants is a good thing, especially when mission-critical systems depend on it. If you're a student or someone just starting out, I point you towards the title of the Cryptofails article linked above: _Write Crypto Code! Don't Publish It._
