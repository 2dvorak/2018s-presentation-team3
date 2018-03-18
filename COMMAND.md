## How to use GnuPG?
 
1. 키 쌍 만들기

```
$ gpg --gen-key
```

2. 목록 보기

```
- 키 목록 : $ gpg --list-keys
- 서명 목록 : $ gpg --list-sigs
```

3. 공개키 내보내기 및 가져오기
```
3.1 파일
  - 내보내기 : $ gpg --export <key ID or identity>
	      $ gpg --armor --export <key ID or identity>  * *ASCII* *
  - 가져오기 : $ gpg --import <key file>

3.2 서버
  - 내보내기 : & gpg --send-key --keyserver keyserver.ubuntu.com <key ID>
  - 가져오기 : & gpg --recv-key --keyserver keyserver.ubuntu.com <key ID>
```

4. Fingerprint 체크
```
$ gpg --fingerprint <key ID>
```
5. 서명하기
```
& gpg --edit-ey <key ID>
gpg> sign
gpg> save

또는

& gpg --sign-key <key ID>
```
6. 서버 새로고침
```
$ gpg --keyserver keyserver.ubuntu.com --refresh-keys
```

7. Web of trust visualization
```
& gpg --list-sigs | sig2dot > phillylinux.dot
& neato -Tps phillylinux.dot > phillylinux.neato.ps
& dot -Tps phillylinux.dot > phillylinux.dot.ps
& convert phillylinux.neato.ps phillylinux.neato.jpg
& convert -geometry 320x240 phillylinux.neato.ps phillylinux.neato.320.jpg
```

8. 암호화 및 복호화
```
- 암호화 : & gpg --encrypt <fime> 
	  & gpg --armor --encrypt <file>  * *ASCII* *

- 복호화 : & gpg <암호화된 파일>
	  & gpg -o <복호화하여 저장할 파일> -d <암호화된 파일>
```

