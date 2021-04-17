# ansible-role-electrs

electrs(Monacoin)用のAnsibleのrole

必ずrootか、sudoを使えるようにしてください。

# 使い方

わからない人は付属のシェルスクリプトを使ってください。よしなにやってくれます。

わかる人は(sudo) ansible-playbook electls.ymlで動くはずです。

# tagsについて

今のところtagsはないですが、もしかしたらupdate用のtagsを用意するかもしれないです。

# role実行前に必ず行うべきこと

かならずdefault/main.ymlの、domain: 'example.com'のexample.comの部分と、

email_address: 'monacoin@example.com'のmonacoin@example.comの部分を、ご自身のものに変更してください。

必要に応じてポートを開放してください。

# よく使いそうなもの

sudoのパスワードを入力する必要がある場合は--ask-become-passを付けて起動するなどしてください(これはこのroleに限りませんが)。

## 特殊な条件時

特定の作業のみを行いたい場合は、ansible-playbook electrs.yml --stepのように実行するか、

場所がわかる場合はansible-playbook electrs.yml --start-at='task_name' --stepのように実行してください。

また、coind用の何かしらの環境変数を入れておく必要がある場合は/etc/systemd/monacoin.serviceを書き換える等で対処してください。

## その他

今後もしかしたらupdate用のタグとかを用意するかもしれないです(思ったより好評だったら)。
