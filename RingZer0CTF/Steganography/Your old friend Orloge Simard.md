<h1><b>Your old friend Orloge Simard</h1></b>
<pre>
<a href="https://ringzer0ctf.com/files/090d249709d7519ebb09cb606d1719a1.zip">File</a>
</pre>
</b><h3>Solution</h3></b>
<p>Buka file dengan sonic-visualizer dan add spectogram <b>Tab Layer --> Add Spectogram</b></p>
<p align='center'>
<img src="https://github.com/enomarozi/RingZer0CTF/blob/master/Steganography/Image/Your%20old%20friend%20Orloge%20Simard.jpg">
</p>
<p>Pada spectogram terdapat encoding morse terbalik, reverse code morse dan decode</p>

```python
morse ={"A":".-","B":"-...","C":"-.-.","D":"-..","E":".","F":"..-.","G":"--.",
        "H":"....","I":"..","J":".---","K":"-.-","L":".-..","M":"--","N":"-.",
        "O":"---","P":".--.","Q":"--.-","R":".-.","S":"...","T":"-","U":"..-",
        "V":"...-","W":".--","X":"-..-","Y":"-.--","Z":"--..","1":".----",
        "2":"..---","3":"...--","4":"....-","5":".....","6":"-....","7":"--...",
        "8":"---..","9":"----.","0":"-----","(":"-.--.",")":"-.--.-"}


data = ". ...- -- -. ---. -. - .. --- -- . .- .- --- ..- .-- -. ..-. .-.."[::-1].split(" ")
for j in data:
    for key, value in morse.items():
        if value == j:
            print(key,end="")
```
</b><h3>Flag</h3></b>
<pre>
FLAGDONNEMOITAJAMBE
</pre>
