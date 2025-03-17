# PicoCTF Challenges - Walkthrough

## Verify

1. Connect to the remote server:
   ```sh
   ssh -p 64405 ctf-player@rhea.picoctf.net
   ```
2. Enter the password: `83dcefb7`
3. List available files:
   ```sh
   ls
   ```
4. Compute the SHA-256 checksum:
   ```sh
   sha256sum files/* | grep 467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02
   ```
5. If the checksum matches, proceed to decryption:
   ```sh
   ./decrypt.sh files/c6c8b911
   ```
6. The flag is revealed: `picoCTF{trust_but_verify_c6c8b911}`

## Scan Surprise

1. Extract the zip file:
   ```sh
   unzip challenge.zip
   ```
2. Decode the QR code with zbar-tools:
   ```sh
   zbarimg home/ctf-player/drop-in/flag.png
   ```
3. The QR code reveals the flag: `picoCTF{p33k_@_b00_a81f0a35}`

## Binary Search

1. Use SSH to access the challenge environment:
   ```sh
   ssh -p 58124 ctf-player@atlas.picoctf.net
   ```
2. Enter the password: `84b12bae`
3. List the files:
   ```sh
   ls
   ```
4. Enter a number to guess between 1-1000, starting with 500, then adjust based on feedback until the correct number is found.
5. The flag is revealed: `picoCTF{g00d_gu355_2e90d29b}`

## Heap 0

1. Download and run the binary file `chall`.
2. Choose option `2` (Write to buffer) and enter a long input to overwrite `safe_var`.
3. Choose option `4` (Print Flag) to reveal the flag.
4. If no flag appears, connect to the remote challenge using:
   ```sh
   nc tethys.picoctf.net 55936
   ```
5. Repeat the steps, and the flag is revealed: `picoCTF{my_first_heap_overflow_4fa6dd49}`

## Format String 0

1. Connect using netcat:
   ```sh
   nc mimas.picoctf.net 63107
   ```
2. Enter the correct burger recommendation by trial and error.
3. The flag is revealed: `picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_c8362f05}`

## Time Machine

1. Download and extract `challenge.zip`:
   ```sh
   unzip challenge.zip
   ```
2. Navigate to the extracted folder:
   ```sh
   cd drop-in
   ```
3. View the commit history:
   ```sh
   git log --oneline
   ```
4. The flag is found in the commit message: `picoCTF{t1m3m@ch1n3_d3161c0f}`

