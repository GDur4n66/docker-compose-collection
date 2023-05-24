# docker-compose-collection
自分で作ったりしたdocker-compose.ymlを保管する

LightningNode<br>
ライトニングノードLNDとLND管理ツールThunderhubで構成。<br>
LNDはneutrinoを使うのでbitcoindは不要。<br>
9735番は他のライトニングノードから接続されるための待ち受けポート。外部から接続できるようにすること。<br>
LNDのAPIポートである10009,8080番とThunderhubの3000番まで開けるかは任意だが、WireGuardやTailscaleなどVPNを使用して自分だけ利用できる方がセキュリティ的に望ましいと思う。

saisho_cln_signet<br>
自ホストにsignet nodeがあり、rpc-allow=172.17.0.0/16でrpcを0.0.0.0にバインドしていること<br>
CLNコンテナから0.0.0.0:38332へ接続する<br>

testnet-isshiki<br>
pi4ユーザのホームディレクトリ/home/pi4にこれらを展開<br>
bitcoinのテストネットで初期同期が終わったら、electrsでDB構築し,mempoolでブロックエクスプローラが事項可能に。<br>
clnでCore-lightning、rtlでRide-The-Lightningを展開してGUIでCLNを管理する。

cln-testnet-arm64<br>
ラズパイ4でbitcoind, cln, torで構成する。<br>
clnが自分で作ったv0.12.1のイメージ担ってる。
