# 概要
第七回の課題提出です。   
発生したエラーと解決方法も記載されました。

# 環境
Windows 10 Pro  
19045.3448

## WSL を使用して Windows に Linux をインストール
 *[Mircosoftサイト](https://learn.microsoft.com/ja-jp/windows/wsl/install)を参照*    
 ```
 wsl --install
```
成功しました。

```
wsl -l -v
```
実行している WSL のバージョンを確認したら、1　でした。
```
wsl --set-version Ubuntu 2
```
 コマンドを使い、バージョンを指定しようとしたら、できませんでした。　　
 
> Error code: Wsl/Service/CreateInstance/WSL_E_WSL2_NOT_SUPPORTED

**解決方法**
1. Task Manager -> More Details
2. Performance -> CPU
3. Virtualization:Enabaled　になってるか確認します
4. なってない場合は再起動してBIOSメニュー
5. Master boardによるですけど起動します前の画面で *F2* が一般的
6. 「Advanced」→「CPU Configuration（CPU設定）」→「Intel（(VMX）Virtualization Technology」の「Disabled」を「Enable」に変更して
7. 「F10」を押して保存すれば完了
8. 注意：お使いのCPUがAMD CPUの場合は、BIOSページに入った後、「CPU Configuration」→「Secure Virtual Machine」或いは「SVM mode」の「Disabled」を「Enable」に変更して、「F10」を押して保存すれば完了
   ![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/f3146a14-bf0e-4c27-8d45-0d1a831afea5)

## Microsoft Store から Windows Terminalをインストール
![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/1364f4c8-47b6-4a46-a581-b4af26608d82)
Windows TerminalでUbuntuとgitが使えるようになりました。

## Dockerの準備
![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/73c4ff6e-af06-4594-b0ad-37b69305a982)
https://docs.docker.com/desktop/troubleshoot/overview/#diagnose-from-the-terminal
のからダウンロードします。
- 注意点
- Docker をインストールしますには __WSL のインストールを終えた後__

## MySQL hands on

- レポジトリをcloneします。
- コンテナを起動します。  
- コンテナを確認します。  
- MySQLにログインします。
![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/2bf05eaa-58ef-4ffc-a407-d65a38de29c4)

以下のようにMySQLにログインできています。  

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/cd5e2265-4c44-449f-a39f-9faa58e692d0)

パスワードが間違えると、以下のエラーが起こります。
> Unit mysqld.service could not be found.

movie_listがあることを確認します。    

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/0cf3ed6f-3b82-44a3-b124-f9dd9277e500)

ちなみに、セミコロン入力忘れるとこうなります。

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/c47c350a-7c7f-4526-9890-882d31d11ab6)


movie_listの利用を開始します。  

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/0c15bcaf-ae49-4039-8474-1c3c1f8fff7c)


moviesテーブルがあることを確認します。

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/0105e4bc-4271-4b57-96bc-4f937f38195d)


moviesテーブルのレコードを確認します。

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/8dfc8ab1-dae0-47fb-b295-bb0f77af9155)

テーブルにレコードを追加してみます。
![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/7508a94d-58ee-4ecd-8dc0-a6329db20fa3)

レコードの登録結果を確認します。

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/903c8a06-7ea0-4393-9f61-d7f23db53f98)

- ログアウトします
- 起動したDockerコンテナを停止します
- 停止できていることを確認します

![image](https://github.com/Mie-ee/mysql-hands-on/assets/146546228/5c04b921-745b-4734-ae50-89963a89455a)



お疲れさまでした！  
