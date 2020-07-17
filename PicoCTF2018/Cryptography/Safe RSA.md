<h1><b>Safe RSA</h1></b>
<pre>
Now that you know about RSA can you help us decrypt this <a href="https://2018shell.picoctf.com/static/ab772a2740031b404eba8d0cc76b43f2/ciphertext">ciphertext</a>? 
We don't have the decryption key but something about those values looks funky..
</pre>
</b><h3>Solution</h3></b>
<p>Pada soal diberikan modulus(n), eksponen(e) dan ciphertext(c)</p> 
<pre>
n : 374159235470172130988938196520880526947952521620932362050308663243595788308583992120881359365258949723819911758198013202644666489247987314025169670926273213367237020188587742716017314320191350666762541039238241984934473188656610615918474673963331992408750047451253205158436452814354564283003696666945950908549197175404580533132142111356931324330631843602412540295482841975783884766801266552337129105407869020730226041538750535628619717708838029286366761470986056335230171148734027536820544543251801093230809186222940806718221638845816521738601843083746103374974120575519418797642878012234163709518203946599836959811
e : 3
c : 2205316413931134031046440767620541984801091216351222789180535786851451917462804449135087209259828503848304180574549372616172217553002988241140344023060716738565104171296716554122734607654513009667720334889869007276287692856645210293194853 
</pre>
<p>Sepertinya itu RSA small-exponent, keuntungan small-exponent(e) yaitu untuk mengurangi waktu encryption. Tetapi small-exponent(e) sangat mudah diprediksi nilai dari
privatekey(d) yang apalagi jika pesannya pendek. disini terdapat penyerangan terhadap small-exponent(e) yaitu <a href="https://en.wikipedia.org/wiki/Coppersmith%27s_attack">Coppersmith's attack</a></p>

```python
import gmpy2

n = 374159235470172130988938196520880526947952521620932362050308663243595788308583992120881359365258949723819911758198013202644666489247987314025169670926273213367237020188587742716017314320191350666762541039238241984934473188656610615918474673963331992408750047451253205158436452814354564283003696666945950908549197175404580533132142111356931324330631843602412540295482841975783884766801266552337129105407869020730226041538750535628619717708838029286366761470986056335230171148734027536820544543251801093230809186222940806718221638845816521738601843083746103374974120575519418797642878012234163709518203946599836959811
e = 3
c = 2205316413931134031046440767620541984801091216351222789180535786851451917462804449135087209259828503848304180574549372616172217553002988241140344023060716738565104171296716554122734607654513009667720334889869007276287692856645210293194853
with gmpy2.local_context(gmpy2.context(), precision=800) as ctx:
    root = gmpy2.cbrt(c)
print(bytes.fromhex(hex(int(root))[2:]).decode("ascii"))
```
<h3><b>Flag</b></h3>
<pre>
picoCTF{e_w4y_t00_sm411_34096259}
</pre>