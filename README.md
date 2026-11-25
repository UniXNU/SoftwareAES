# SoftwareAES

Software AES-CBC through IOAESAccelerator.

built into the kernel and used by the sheng crypto path.

A request is processed in 4096-byte pieces through a kernel buffer, each piece
with its own key schedule, by the kernel's `aes_encrypt_cbc` and
`aes_decrypt_cbc` (the registered corecrypto). `native_aes_completed`,
`native_aes_bytes` and `native_aes_ticks` count the completed requests, their
bytes and the time spent in them; `native_aes_nonce_key_uses`,
`native_aes_fairplay_key_uses`, `native_aes_unsupported_key` and
`native_aes_last_unsupported_selector` record per-device `0x8a4`/`0x899` key
derivations and refused hardware selectors.

Build and interface details: [documentation](https://unixnu.com/drivers/software-aes). Component sources and dependencies: [catalog](https://unixnu.com/reference/components).
