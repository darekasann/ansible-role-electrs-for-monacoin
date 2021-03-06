# English

Installing electrs for Monacoin

Please run as root or use sudo.

## Usage ( for Ubuntu )

1. Install Ansible and Git

sudo apt install ansible git

2. Clone from repository

git clone https://github.com/darekasann/ansible-role-electrs-for-monacoin.git

3. Edit config

cd ansible-role-electrs-for-monacoin

nano role/electrs/defaults/main.yml

Then, edit domain and email_address.

If you install electrs for another host, edit electrs.yml.

nano electrs.yml

hosts: localhost -> your.domain.com

4. Run Ansible

sudo ansible-playbook electrs.yml

# Japanese

electrs(Monacoin)用のAnsibleのrole

必ずrootか、sudoを使えるようにしてください。

## 使い方(Ubuntu用)

他のディストリビューションの場合は適宜置き換えてください。

1. AnsibleとGitをインストールする

sudo apt install ansible git

2. ファイルをコピーする

git clone https://github.com/darekasann/ansible-role-electrs-for-monacoin.git

3. 設定を変える

cd ansible-role-electrs-for-monacoin

nano role/electrs/defaults/main.yml

domainとemail_addressをご自身のものに変更してください。

もし他のホストへインストールする場合は、electrs.ymlのlocalhostの部分を書き換えてください。

nano electrs.yml

hosts localhost -> your.domain.com

4. ansibleを実行する

cd ansible-role-electrs-for-monacoin

sudo ansible-playbook electrs.yml

## role実行前に必ず行うべきこと

かならずdefault/main.ymlの、domain: 'example.com'のexample.comの部分と、

email_address: 'PLAYMONA_is_good@example.com'のPLAYMONA_is_good@example.comの部分を、ご自身のものに変更してください。

また、必要に応じてiptablesやufwでポートを開放したり閉じたりしてください。

sudoのパスワードを入力する必要がある場合は--ask-become-passを付けて起動するなどしてください(これはこのroleに限りませんが)。

### 特殊な条件時

特定の作業のみを行いたい場合は、ansible-playbook electrs.yml --stepのように実行するか、

場所がわかる場合はansible-playbook electrs.yml --start-at='task_name' --stepのように実行してください。

また、coind用の何かしらの環境変数を入れておく必要がある場合は/etc/systemd/monacoin.serviceを書き換える等で対処してください。

### その他

今後もしかしたらupdate用のタグとかを用意するかもしれないです(思ったより好評だったら)。
