<h1><b>I love cat</h1></b>
<pre>
I love cat! Do you?

User: cat
Password: cat
ssh://challenges.ringzer0team.com:10252
</pre>
</b><h3>Solution</h3></b>
<p>Connect ssh, dan eksekusi perintah cat dengan option -A(cetak semua) atau -v(cetak termasuk strings non-printing) pada terminal server</p>

```console
root@Python:/home/venom/Downloads# ssh cat@challenges.ringzer0ctf.com -p 10252
The authenticity of host '[challenges.ringzer0ctf.com]:10252 ([78.109.87.50]:10252)' can't be established.
ECDSA key fingerprint is SHA256:ay3OoeHJOwmJrQs+ug/kjJHyNCaV3hUcxrqat7jmFI8.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[challenges.ringzer0ctf.com]:10252,[78.109.87.50]:10252' (ECDSA) to the list of known hosts.
cat@challenges.ringzer0ctf.com's password: 

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

-rbash: /usr/bin/groups: Permission denied
cat@lxc-forensics-252:~$ ls
commands  flag.txt
cat@lxc-forensics-252:~$ cat flag.txt 
**************************** WHERE IS THE FLAG ? ****************************
cat@lxc-forensics-252:~$ cat -A flag.txt 
FLAG-0K14eDrm4t5g7KD54X8Dl3NNcZ956oCK^M**************************** WHERE IS THE FLAG ? ****************************$
```
</b><h3>Flag</h3></b>
<pre>
FLAG-0K14eDrm4t5g7KD54X8Dl3NNcZ956oCK
</pre>
