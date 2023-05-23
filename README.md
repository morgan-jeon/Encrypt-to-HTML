# Encrypt-to-HTML

#### Simple implementation of  files embedding to HTML as a blob, with AES-CBC Encryption. 



## Features

- Embeds any file type into an HTML as a Base64-encoded blob.
- Provides AES-CBC encryption for the embedded file.
- Embeds CryptoJS in the HTML for offline decryption.
- Includes password verification functionality using random test data.

## Requirements

- Python 3
- Crypto (`pip install pycryptodome`)
- Jinja2 (`pip install Jinja2`)

## Usage

```
python3 encrypt-to-html.py <input_file> <key> [output_file] [output_template]
```

- `<input_file>`: The file you want to encrypt and embed.
- `<key>`: The encryption key. It is hashed to a 256-bit key using SHA256.
- `[output_file]`: Optional. The output HTML file. If not provided, the output file will be named as `<input_file>-enc.html`.
- `[output_template]`: Optional. A custom Jinja2 HTML template file to use instead of the default embedded template.

## Note

The generated HTML file uses the CryptoJS library for decryption. This library is embedded in the HTML, ensuring the decryption process can be done offline.

## Example

To encrypt and embed a file named `example.txt` with the key `example_key`, you would run: `python3 Encrypt-to-HTML.py example.txt example_key`

This will create an HTML file named `example.txt-enc.html` containing the encrypted and embedded file, which can be decrypted using the provided key.

## License

This project is licensed under the terms of the MIT license.

