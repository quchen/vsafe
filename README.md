vsafe - Very Simple Asymmetric File Exchange
============================================

Workflow
--------

*Alice* wants to send *Bob* a file.

  1. *Bob* generates a keypair.
     ```sh
     vsafe keygen bobs-key
     ```

  2. *Bob* sends *Alice* his pubkey (bobs-key.pub), e.g. via email.

  3. *Alice* encrypts her data using *Bob*’s pubkey.
     ```sh
     vsafe encrypt bobs-key.pub alice-secret.txt > encrypted.txt
     ```

  4. *Alice* sends the encrypted file to *Bob* (encrypted.txt).

  5. *Bob* decrypts the file using his pubkey. He can do so by following the
     instructions contained in the file, or by simply running it as a script,
     since it is a runnable decryption program.

     ```sh
     chmod +x encrypted.txt
     ./encrypted.txt bobs-key > alice-secret.txt
     ```

Command overview
----------------

  - vsafe help
  - `vsafe encrypt PUBKEY FILE` – Encrypt FILE to stdout using PUBKEY file
  - `vsafe keygen FILE` – Generate keypair: FILE, FILE.pub
