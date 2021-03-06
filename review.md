# Webについて
---
### プロトコルとは何か説明してください。
コンピューター同士の通信の取り決め。共通の規格を用意する事で、異なる機器であっても通信が行えるようにできるようにしている。

### httpとhttpsの違いについて説明してください。
HTTPリクエストとHTTPレスポンスを暗号化して通信するか否かの違い。どちらもWEBサイトを表示するためのプロトコルで、HTTPSが暗号化するプロトコル（HTTPSのSはSecureの事）。SSLサーバ証明書をサーバにインストールすると暗号化通信が可能になる。

### Webサーバがどのような役割を持っているかについて説明してください。
クライアントからのリクエストに応じてHTMLや画像などをレスポンスとして返すこと。

### クライアントとサーバの違いについて説明してください。
HTTPレスポンスをクライアントに返してサービスを提供する側のコンピュータがサーバ、HTTPリクエストをサーバに送ってサービスを受ける側のコンピュータをクライアントと呼ぶ。

### URLにアクセスして動的なウェブサイトの画面が表示されるまでの流れを説明してください。
1. クライアントがWEBサーバ）にURLでHTTPリクエストを送る
2. WEBサーバがHTTPリクエストを受け取り、アプリケーションサーバにリクエストを送る。
2. アプリケーションサーバがWEBサーバから受け取ったリクエストを元にデータベースサーバにSQLを実行する。
3. データベースサーバがアプリケーションサーバから受けたSQLを実行した結果（データ）をアプリケーションサーバに返す。
4. アプリケーションサーバがデータベースサーバから受け取ったデータを元にサーバサイド言語ファイルを実行し、実行結果をWEBサーバに返す。
5. WEBサーバがアプリケーションサーバから受け取った事項結果を元に、クライアントにHTTPレスポンスを返す。
6. クライアントがWEBサーバから受け取ったHTTPレスポンスから動的なWEBサイトが表示される。

# Apacheについて
---
### Apacheとはどのようなソフトウェアか説明してください。
コンピュータがWEBサーバとしてHTTPリクエストを受け取りHTTPレスポンスを返すためのソフトウェアの一つ。同時アクセスに強いNginxに対して、Apacheは負荷の軽さとセットアップの容易さが特徴。

### DocumentRootがどのような役割を持ったディレクティブか説明してください。
WEB上に公開するサーバ内のディレクトリを設定するディレクトリ。DocumentRootディレクティブの値として設定されたディレクトリが公開対象になる。また初期設定では/var/www/htmlディレクトリが公開されるようになっている。

### Indexがどのような役割を持ったディレクティブか説明してください。
クライアントからリクエストがあった場合にどのファイルをクライアントにHTTPレスポンスとして返すかを定めるためのディレクティブ。初期設定ではindex.htmlを返すようになっている。

# Dockerについて
---
### Dockerとはどのようなソフトウェアか説明してください。
仮想環境をコンテナという型で簡単に作成や実行することができるソフトウェア。開発者とは異なるOSを想定した環境（仮想環境）を用意して開発することで、本番環境と開発環境や開発者間との環境の差異をなくすことができるのでアプリの挙動など揃えられるメリットがある。

### Docker-Composeとはどのようなソフトウェアか説明してください。
Dockerの拡張ツール。単一のコンテナを取り扱うDockerに対し、Docker-Composeでは複数のコンテナの起動や削除などの操作を一括で行うことができる。

### Dockerにおけるコンテナとはどのようなものか説明してください。
ゲストOSを用意せずにアプリやソフトを開発・実行するための環境。

### Dockerにおけるイメージとはどのようなものか説明してください。
コンテナを作成するための設計図。設定の異なるイメージを使うことで、様々な環境を想定したコンテナを用意することが出来る。

### DockerにおいてDockerfileは何のために使用するか説明してください。
もともとDockerhubで用意されているイメージから作られる環境とは異なる環境を用意したいとき。もともと用意されているベースイメージを元に設定ファイルなどを用意することでオリジナルのイメージをBuildすることができる。

### Dockerのボリュームマウントは何のために使用するか説明してください。
コンテナ内にある残していきたいデータ（アプリのコードやDBのレコード等）を永続的に保持するため。コンテナを破棄する際にコンテナ内のデータは全て消えてしまうので、指定したディレクトリにコンテナ内で指定したディレクトリを同期することで保持を実現している。

# ネットワークについて
---
### ドメインとは何か説明してください。
インターネット上におけるコンピュータやネットワークを識別するためにつけられる名前。インターネットにおける住所に相当し、URLやメールアドレスに使われる。

### ホスト名とは何か説明してください。
ネットワーク上におけるコンピュータを識別するためにつけられる名前。また、ネットワークとはコンピュータどうしを接続して相互にやり取りするコンピュータの集合体を指す。

### ポートとは何か説明してください。
コンピュータにおいて通信が出入りする役割を持つドア。ポートにはポート番号が振られており、通信の種類によって適切なポートに通信先を振り分ける事によって通信を行うことが出来る。

### ポートフォワードとは何か説明してください。
特定のポート番号に宛に送られてきた通信をあらかじめ設定していたコンピュータに転送する機能。これにより外部と通信するコンピュータを一つに絞れるため、ネットワーク内のパソコン全てが外部と通信する必要がなくなるため、セキュリティ上安全な上に管理も楽になる。

### 127.0.0.1というIPアドレスが何か説明してください。
自分自身を表すループバックアドレスと呼ばれるIPアドレスの一つ。各通信機器にはIPアドレスというインターネット上の住所が割り当てられており、127.0.0.1＝自身の通信機器固有のIPアドレスとして変換して扱える。

### localhostとは何か説明してください。
ネットワーク通信における位置関係の一つで、自身の通信端末のことを指す。ちなみに通信相手はremote hostと呼ばれる。