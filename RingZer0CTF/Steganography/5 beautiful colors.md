<h1><b>5 beautiful colors</h1></b>
<pre>
<a href="https://ringzer0ctf.com/files/bf581c561411f3e3aeeb45e93a3880e9.zip">File</a>
</pre>
</b><h3>Solution</h3></b>
<p>Cari image original sesuai soal dengan google image search, disini saya mendapatkan imagenya walaupun beda size</p>
<p>Image Original</p>
<p align='center'>
  <img src="https://github.com/enomarozi/Writeup-CTF/blob/master/RingZer0CTF/Steganography/Images/Real_image.png">
</p>
<p>Image Fake(challenge)</p>
<p align='center'>
  <img src="https://github.com/enomarozi/Writeup-CTF/blob/master/RingZer0CTF/Steganography/Images/41250d2f058fcf724ecef0ee6e92ef10.png">
</p>
<p>Perbedaan dari kedua gambar yaitu pada matrix disudut kanan bawah, dan jika dicetak RGB pada masing-masing matrik kecuali warna putih yaitu</p>
<pre>
[112 30 30],[119 10 30],[110 30 30],[101 30 10],[100 70 30]
</pre>

```python
data = [112,119,110,101,100]
for i in data:
    print(chr(i),end="")
```
</b><h3>Flag</h3></b>
<pre>
pwned
</pre>
