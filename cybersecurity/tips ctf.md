its possile that the something is encrypt two time
example with interdec challenge in picoctf
- the challenge give file that contain this string: `YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzVNR3N5TXpjNWZRPT0nCg==`
- after it was decrypt using From **Base64** in cybercheft, this appear: `b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg5MGsyMzc5fQ=='`
- remove `b'` at the start and `'` at the end then decrypt it again with **Base64**
- this will appear: `wpjvJAM{jhlzhy_k3jy9wa3k_890k2379}`
- at this point the shape of flag string usually looks like is appearing but still decrypted with caesar. the final thing to do is decrypt it with **ROT13**
- the flag will appear after decrypt with ROT13 with 19 amount: `picoCTF{caesar_d3cr9pt3d_890d2379}`
> this challange also has the caesar tag and base64 in the picoctf challange library.
> when using ROT13 the user should try to play with the amount