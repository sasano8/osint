# osint
公開情報を利用した情報収集についての知見をまとめる。

# security exploit

## https://www.exploit-db.com/google-hacking-database
ハックに有益なgoogleクエリのデータベース



# forensic
```
# pagefile.sysの解析

# 参考
https://soji256.hatenablog.jp/entry/2019/06/25/065200

# ファイルパス
strings pagefile.sys | grep -i "^[a-z]:\\\\" | sort | uniq > list_file.txt


# URL
strings pagefile.sys | egrep "^https?://" | sort | uniq > list_url.txt

# メールアドレス
strings pagefile.sys | egrep '([[:alnum:]_.-]{1,64}+@[[:alnum:]_.-]{2,255}+?\.[[:alpha:].]{2,4})' > list_mail.txt


# 環境変数
strings pagefile.sys | grep -i "^[a-zA-Z09_]*=.*" | sort -u | uniq > list_envirnoment.txt
```
