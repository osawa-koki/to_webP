# to_WebP

画像をWebP形式に変換するサイト。  
主目的は[GitHub codespaces](https://docs.github.com/ja/codespaces)の学習。  

[GitHub codespaces](https://docs.github.com/ja/codespaces)は、GitHub上でコードを編集するためのオンラインIDEです。  
[GitHub codespaces](https://docs.github.com/ja/codespaces)を使って、このサイトを作成しました。  

## 実行方法

```shell
# デバグ実行
dotnet run --project ./server

# Dockerで実行
docker build -t to-webp . && docker run -p 8080:8080 -it --rm --name my-to-webp to-webp
```

## イロイロ

### GPG署名

codespacesを使用したコミットはデフォルトでGPG署名がオフになっている。  
これに署名をするには「設定 - Code, planning, and automation - GPG verification」をオンにする。  

変更するボタンがないんだけど、ラジオボタンを変更しただけでok?  
認証されないよ、、、  

「All repositories」ではなく、「Selected repositories」に変更してみた。  
署名されないや、、、  

英語版でも同様の説明なのに、、、  
いったんあきらめる。  

---

シェルからGPGキーを作成してみる。  
さすがにこれはいけると思うけど、、、  

[GitHubへのコミットに対して認証をしてみる。](https://github.com/osawa-koki/verified-commit)  

```shell
gpg --full-generate-key
```

codespaces上でのユーザ名とメールアドレスの設定も必要。  

### パフォーマンス

~~少し遅いかも、、、~~  

かなり遅い。  
便利なんだけどね、、、  

<https://github.com/osawa-koki/to_WebP/codespaces>から「マシンタイプ」の変更ができるけど、いまあるのは以下の2種類のみ。  
どっちも遅いように感じる。  

- 2-core | 4GB RAM • 32GB
- 4-core | 8GB RAM • 32GB

Gitが操作できないから、ターミナル上でやらざるを得ない、、、  
変更が反映されるのにも相当時間がかかる、、、  

めんどくさいから、`git add . && git commit -m "🥺🥺🥺" && git push`このコマンドを常に打てるようにしておく。  
本末転倒とはまさにこのこと。  

### ブラウザタブのアイコン変えてほしい、、、

複数のGitHubのページをを開いていると、それがコードスペースのタブ化が分からなくなってしまう。  
専用のアイコンが欲しい、、、  
