# What's The Password

My friend gave me this file, he said there was something hidden

# Solution

```bash
➜  images git:(main) ✗ steghide info sudo.jpg
"sudo.jpg":
  format: jpeg
  capacity: 5.6 KB
Try to get information about embedded data ? (y/n) y
Enter passphrase:
  embedded file "steganopayload457819.txt":
    size: 39.0 Byte
    encrypted: rijndael-128, cbc
    compressed: yes
➜  images git:(main) ✗ cat steganopayload457819.txt
cat: steganopayload457819.txt: No such file or directory
➜  images git:(main) ✗ steghide extract -sf sudo.jpg
Enter passphrase:
wrote extracted data to "steganopayload457819.txt".
➜  images git:(main) ✗ cat steganopayload457819.txt
CYCTF{U$3_sud0_t0_achi3v3_y0ur_dr3@m$!}%
```

# Flag

`CYCTF{U$3_sud0_t0_achi3v3_y0ur_dr3@m$!}`
