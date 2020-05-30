---
layout: post
title: Tokenize a unicode text file and find word frequency
---

```
CHARS=$(python -c 'print (u"\u0621\u0622\u0623\u0624\u0625\u0626\u0627\u0628\u0629\u062A\u062B\u062C\u062D\u062E\u062F\u0630\u0631\u0632\u0633\u0634\u0635\u0636\u0637\u0638\u0639\u063A\u063B\u063C\u063D\u063E\u063F\u0640\u0641\u0642\u0643\u0644\u0645\u0646\u0647\u0648\u0649\u064A".encode("utf8"))')
```

```
sed 's/[^'"$CHARS"']/\n/g' < text.txt | sort | uniq -c |  sort -n -r > sorted.txt
```

Notes:
* to get hex value of unicode char:  echo -ne '\u0621' | xxd
* this regex can be used too sed 's/\xc2\x91\|\xc2\x92\|\xc2\xa0\|\xe2\x80\x8e//'
