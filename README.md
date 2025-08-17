# How to Run


## Requirements

Make sure you have **Python 3.7+** installed.

Install required dependencies:

```bash
pip install cryptography
```

1. Clone or download this repository and open a terminal in the project folder.

Run the script:
```
python password_generator.py
```

2. Follow the prompts:

+ Enter the desired password length (minimum 6).

+ Choose which character types to include (uppercase, lowercase, numbers, special characters).

+ Specify how many passwords to generate (1–10).

+ Optionally, choose whether to save passwords to a file.


# Password Generator

This project is a secure password generator that lets you:
- Generate strong passwords with customizable options (uppercase, lowercase, numbers, special characters).
- Save generated passwords securely in an encrypted file using the `cryptography` library.
- Decrypt saved passwords when needed.

