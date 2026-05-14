# ChaCha20Poly1305

ChaCha20とPoly1305によるAEAD暗号化/復号ライブラリ

## 使い方

```js
import { AEAD } from "~~https://code4fukui.github.io/ChaCha20Ploy1305/AEAD.js~~ *(unavailable)*";

const key = new Uint8Array(32);
const nonce = new Uint8Array(12);
const plaintext = new TextEncoder().encode("abc");
const aad = new Uint8Array(12);
const [cipher, tag] = AEAD.encrypt(key, nonce, plaintext, aad);

const plaintext2 = AEAD.decrypt(key, nonce, cipher, aad, tag);
console.log(new TextDecoder().decode(plaintext2));
```

## 参考

- ChaCha20
    - 2014年にDevi Mandiriによって作成。パブリックドメイン。
    - 実装は chacha-ref.c version 20080118 から派生
    - 詳細はこちら: http://cr.yp.to/chacha/chacha-20080128.pdf
- Poly1305
    - 2014年にDevi Mandiriによって作成。パブリックドメイン。
    - 実装は poly1305-donna-16.h から派生
    - 詳細はこちら: https://github.com/floodyberry/poly1305-donna

## ライセンス

MIT License — 詳細は [LICENSE](LICENSE) を参照してください。
