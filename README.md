# Client Preview

A password-protected preview page hosted on GitHub Pages.

The page content is encrypted (AES-256-GCM, key derived with PBKDF2-SHA256, 600k iterations) in `payload.enc.json`. `index.html` is a small gate that decrypts it in the browser once the correct password is entered. The password is not stored in this repo.

## Rebuild

```bash
node encrypt.mjs source.html '<password>'
git commit -am "Rebuild payload" && git push
```

`source.html` is the plaintext and is gitignored. Never commit it.
