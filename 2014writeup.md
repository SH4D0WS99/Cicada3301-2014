# Cicada 2014 puzzle

Date: 11-10-2021 | Author: @SH4D0WS99

## 1. 2014.jpg
1. Downloaded the image from imgur.
2. Ran Outguess revealed the file ```2014.out```.
3. The message contained a clue to a book and a bookcipher.
4. The clue led to the book ```Self-Reliance and Other Essays``` by ```Ralph Waldo Emerson```.

## 2. Self-Reliance and Other Essays bookcipher
1. Book cipher revealed the first onion URL: ```auqgnxjtvdbll3pv.onion```.

## 3. 1st Onion deep web link
1. Website revealed ```1033.jpg```.
2. Ran Outguess revealed the file ```1033.out```.
3. The file ```1033.out``` contains a RSA message.

## 4. RSA cipher
1. Found out the p and q needed: ```p = 97513779050322159297664671238670850085661086043266591739338007321, q = 77506098606928780021829964781695212837195959082370473820509360759```.
2. Create a Perl script to decrypt the RSA cipher.
3. Decrypting the RSA cipher revealed the second onion URL: ```cu343l33nqaekrnw.onion```.

## 5. 2nd Onion deep web link
1. The webpage revealed a growing string.
2. The string dissappeared and was replaced with huge chunk of data.
3. Download the huge chunk of data and saving as ```onion1.hex```.
4. Obtain hidden files in huge chunk of data with the help of [CyberChef](https://gchq.github.io/CyberChef).
5. CyberChef recipe:
- From Hex.
- XOR with Key: 0xFF.
- Extract Files: only enable Images.
6. Download the 2 images.
7. CyberChef recipe:
- From Hex.
- Reverse.
- XOR with Key: 0xFF.
- Extract Files: only enable Images.
8. Download 1 image.
9. The last image contains a page with runes.
10. Translating this runes obtains rubbish text.
11. Applying the Atbash cipher (simply flipping the runic alphabet from the Gematria Primus) translates to a warning about the book.

## 6. Column Transposition cipher
1. Ran Outguess revealed the file ```image01.out```.
2. Ran Outguess revealed the file ```image02.out```.
3. Ran Outguess revealed the file ```image03.out```.
4. Each ```.out``` file contains a hexadecimal string.
5. Copy hexadecimal string and paste it in a new file.
6. Remove each new line (Find and Replace: Regular expression: "\n").
7. Download the multixor script from GitHub: [multixor](https://github.com/ingeist/multixor)
8. Command the following in your terminal: ```python3 multixor/multixor.py -t image01-hex.txt -t image02-hex.txt -t image03-hex.txt -o message.txt.asc```.
9. Open the ```message.txt.asc``` PGP signed message file.
10. The text has been reordered with a column transposition cipher.
11. By reordering the columns a text can be seen: ```GOOD WORK ULTIMATE TRUTH IS THE ULTIMATE ILLUSION JOIN US AT FV7LYUCMEOZZD5J4ONIO```.
12. The following onion URL can be seen: ```fv7lyucmeozzd5j4.onion```.

## 7. 3rd Onion deep web link
1. Another growing string page was found. Also the server-status webpage was accidentaly available.
2. A huge chunk of hex data was posted to the server-status webpage.
3. Download the huge chunk of data. I saved it as ```server-status.hex```.
4. There are 2 ways to obtain files hidden in the huge chunk of data. With the help of [CyberChef](https://gchq.github.io/CyberChef) or commandline tool xxd. I prefer CyberChef but it is your own choice.
5. CyberChef recipe:
- From Hex
- Extract Files: only enable Images.
6. Download 1 image.
7. Or command the following in your terminal: ```xxd -p -r server-status.hex server-status.bin```.
8. Use commandline tool binwalk to extract files from binary (.bin) file with the following command: ```binwalk -e server-status.bin```.
9. CyberChef recipe:
- From Hex.
- Reverse.
- Extract Files: only enable Images.
10. Download 1 image.
11. Comparing the 2 images revealed that they are exactly the same.
12. The server-status webpage changed and revealed a new huge chunk of data.
13. Download the huge chunk of data. I saved it as ```server-status2.hex```.
14. CyberChef recipe:
- From Hex
- Extract Files: only enable Images.
15. Download 1 image.
16. Or command the following in your terminal: ```xxd -p -r server-status2.hex server-status2.bin```.
17. Use commandline tool binwalk to extract files from binary (.bin) file with the following command: ```binwalk -e server-status2.bin```.
18. CyberChef recipe:
- From Hex.
- Reverse.
- Extract Files: only enable Images.
19. Download 1 image.
20. The images contain 2 pages with runes.
21. Translating the runes with the Gematria Primus obtains rubbish text.
22. The runes are encrypted with a [Vigenère cipher](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher).
23. Applying the key: ```DIUINITY``` revealed a welcome text.
24. Ran Outguess revealed the file ```image5.out```.
25. Running the commandline tool file revealed it is a JPEG image.
26. Rename the file ```image5.out``` to ```image5out.jpg```.
27. The file ```page5.jpg``` was encoded with a Vigenère cipher.
28. Applying the key: ```welcome pilgrim to the``` revealed a new onion URL.
29. The following onion URL can be seen: ```avowyfgl5lkzfj3n.onion```.

## 8. 4th Onion deep web link
1. Another growing string page was found.
2. CyberChef bugs with this process for some reason so I will be using xxd.
3. Command the following in your terminal: ```xxd -p -r onion4.hex onion4.bin```.
4. Running the commandline tool file revealed it is a Gunzip archive.
5. Rename the file ```onion4.bin``` to ```onion4.gz```.
6. Unzip the ```onion4.gz``` file with the following command: ```gunzip onion4.gz```.
7. CyberChef recipe:
- Extract Files: only enable Images.
8. Download 2 images.
9. CyberChef recipe:
- Reverse
- Extract Files: only enable Images.
10. Download 2 images.
11. The images contain pages with runes.
12. Translating this runes obtains rubbish text.
13. Applying the Atbash cipher (simply flipping the runic alphabet from the Gematria Primus) translates to a koan.
14. Ran Outguess revealed the file ```image9.out```.
15. The text has been reordered with a column transposition cipher.
16. By reordering the columns a text can be seen: ```TO BELIEVE TRUTH IS TO DESTROY POSSIBILITY Q4UTGDI2N4M4UIM59133```.
17. The following onion URL can be seen: ```q4utgdi2n4m4uim5.onion```.

## 9. 5th Onion deep web link
1. The webpage contained another huge chunk of data.
2. Copy the entire hexadecimal string to a notepad and save it.
3. CyberChef recipe:
- From Hex.
- Extract Files: only enable Audio.
4. Download 1 audio MPEG 3 file.
5. Or command the following in your terminal: ```xxd -p -r onion5.hex onion5.bin```.
6. Running the commandline tool file revealed it is a MPEG 3 audio file.
7. Rename the file ```onion5.bin``` to ```onion5.mp3```.
8. Running the commandline tool id3v2 revealed the ID3v2 tags of the MPEG 3 audio file: ```Title: Interconnectedness, Artist: 3301```.
9. The webpage changed and an image file could be seen. This image is a painting of ```Portrait of Andrés del Peral``` by ```Goya y Lucientes```.
10. Ran Outguess revealed the file ```onion5portrait.out```.
11. Running the commandline tool file revealed it is a Bzip2 archive.
12. Rename the file ```onion5portrait.out``` to ```onion5portrait.bz2```.
13. Unzip the ```onion5portrait.bz2``` file with the following command: ```bzip2 -d onion5portrait.bz2```.
14. The following file revealed: ```onion5portrait```.
15. Running the commandline tool file revealed it is a PGP signed message file.
16. The PGP message file contained 3 hexadecimal strings and a book cipher.
17. Copy the first hexadecimal string to a notepad and save it.
18. CyberChef recipe:
- From Hex.
- Extract Files: only enable Images.
19. Download 1 image.
20. Or command the following in your terminal: ```xxd -p -r onion5hex1.hex onion5hex1.bin```.
21. Running the commandline tool file revealed it is a JPEG image file.
22. Rename the file ```onion5hex1.bin``` to ```onion5hex1.jpg```.
23. The equation in the first image is part of the Godel incompleteness theorem.
24. Copy the second hexadecimal string to a notepad and save it.
25. CyberChef recipe:
- From Hex.
- Extract Files: only enable Images.
26. Download 1 image.
27. Or command the following in your terminal: ```xxd -p -r onion5hex2.hex onion5hex2.bin```.
28. Running the commandline tool file revealed it is a JPEG image file.
29. Rename the file ```onion5hex2.bin``` to ```onion5hex2.jpg```.
30. The second image with the eye is a painting by ```M.C. Escher``` called ```Eye```, painted in 1946.
31. Copy the third hexadecimal string to a notepad and save it.
32. CyberChef recipe:
- From Hex.
- Extract Files: only enable Audio.
33. Download 1 audio MPEG 3 file.
34. Or command the following in your terminal: ```xxd -p -r onion5hex3.hex onion5hex3.bin```.
35. Running the commandline tool file revealed it is a MPEG 3 audio file.
36. Rename the file ```onion5hex3.bin``` to ```onion5hex3.mp3```.
37. Running the commandline tool id3v2 revealed nothing.
38. The MPEG 3 audio file is a segment of Bach's Trio Sonata in G Major (BWV 1039).
39. Combining the 3 hints revealed the book ```Gödel, Escher, Bach: An Eternal Golden Braid``` by ```Douglas Hofstadter```.
40. The book cipher revealed a new onion URL.
41. The following onion URL can be seen: ```ut3qtzbrvs7dtvzp.onion```.

## 10. 6th Onion deep web link
1. The webpage contained another huge chunk of data.
2. Copy the entire hexadecimal string to a notepad and save it.
3. CyberChef recipe:
- From Hex.
- Extract Files: only enable Images.
4. Download 4 images.
5. The images contain pages with runes.
6. Applying the Gematria Primus revealed a text about the loss of divinity.
7. Or command the following in your terminal: ```xxd -p -r onion6.hex onion6.bin```.
8. Use commandline tool binwalk to extract files from binary (.bin) file with the following command: ```binwalk -e onion6.bin```.
9. Ran Outguess revealed the file ```image11.out```.
10. Ran Outguess revealed the file ```image12.out```.
11. Ran Outguess revealed the file ```image13.out```.
12. Ran Outguess revealed the file ```image14.out```.
13. Set up a CGI script which accepts uploads and set up a Tor hidden service.
14. Open the file ```interconnectedness.mp3``` in [OpenPuff](https://embeddedsw.net/OpenPuff_Steganography_Home.html).
15. Extract the .txt file and name it ```magicsquares.txt```.
16. Submit the 3 magic squares and your Tor hidden service onion link and download the 3 images.
17. The 3 images with runes are encrypted with a Vigenère cipher.
18. Applying the key: ```FIRFUMFERENFE``` revealed a koan.
19. After a while Cicada 3301 posted a ```message.txt.asc``` to your Tor hidden service.
20. The PGP signed message contained a onion URL.
21. The following onion URL can be seen: ```ky2khlqdf7qdznac.onion```.

## 11. 7th Onion deep web link
1. The webpage contained 57 images numbered 0.jpg to 57.jpg.
2. Download all the 57 images.
3. The image ```57.jpg``` can be translated directly with the Gematria Primus.
4. The image ```56.jpg``` is encrypted with the [Euler totient function](https://en.wikipedia.org/wiki/Euler%27s_totient_function).
5. Decrypting this page revealed that there is a deep web link that hashes to: ```36367763ab73783c7af284446c59466b4cd653239a311cb7116d4618dee09a8425893dc7500b464fdaf1672d7bef5e891c6e2274568926a49fb4f45132c2a8b4```.
