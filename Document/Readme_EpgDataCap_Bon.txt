BonDriverを使用したEPGデータの取得、録画やTSデータのUDP、TCP送信を行う
ためのツールです。
EpgTimerSrv.exe（EpgTimer.exe）からの制御で予約録画を行うこともできます。

最新の変更内容はReadme.txtの更新履歴を参照してください。

■使用前の準備■
　Readme.txtの■基本的な使用準備■を参照

　使用デバイス用のBonDriverを用意し、「BonDriver」 フォルダに入れる。
　BonDriverによってはiniファイルなどで設定できる内容があるので、あ
　らかじめ設定をしておく。


■使い方■
　初期設定、ネットワーク送信、即時録画を行う場合に、単独で起動して使用
　できます。基本的にはEpgTimerからの制御で使用されます。
　予約録画、EPG取得時は、EpgTimerから自動的に起動されます。手動で終了な
　どは行わないでください。
　予約をキャンセルする場合はEpgTimerから予約を削除してください。

　・チューナー
　　　使用するBonDriverを一覧から選択します。

　・サービス
　　　チャンネルスキャンを行っていれば、選択したチューナーで視聴可能な
　　　サービスを一覧から選択できるようになります。設定で表示項目をカス
　　　タマイズすることができます。

　・チャンネルスキャン ボタン
　　　視聴可能なチャンネルをスキャンします。初めて使用するチューナーで
　　　は行ってください。
　　　チャンネル構成が変わった時などにも行ってください。

　・EPGデータ取得 ボタン
　　　EPGデータの取得を行います。あらかじめ設定で取得を行うサービスを選
　　　択しておく必要があります。
　　　地デジでは１チャンネル約１〜２分、BS/CSでは１チャンネル約７分ほど
　　　かかります。
　　　EpgTimerからのEPG取得を行った場合、複数チューナーを使用して高速に
　　　取得が可能なため、そちらを推奨します。

　・設定 ボタン
　　　各種設定を行います。詳しい内容は後述

　・即時録画 ボタン
　　　現在選択中のサービスの録画を行います。録画ファイル名は
　　　「YYYYMMDDHHMMSS-（サービス名）.ts」になります。
　　　録画フォルダは設定であらかじめ指定しておく必要があります。

　・停止時間
　　　即時録画の停止時間を設定できます。録画時間ではなく停止時刻のを入
　　　力し「Set」にチェックを入れると有効になります。

　・キャンセル ボタン
　　　チャンネルスキャン、EPGデータ取得、即時録画処理をキャンセルします。

　・View ボタン
　　　設定したexeファイルを起動します。UDP、TCP受信で視聴可能なアプリの
　　　起動を想定して使います。

　・UDP チェックボタン
　　　設定でUDP送信先がある場合にUDP送信のON/OFFを切替えます。

　・TCP チェックボタン
　　　設定でTCP送信先がある場合にTCP送信のON/OFFを切替えます。

　・次の番組情報を表示
　　　現在選択中のサービスの次の番組情報を表示します。番組一覧と番組情
　　　報の両方が次の番組になります。

　・番組情報
　　　現在放送中 or 次の番組情報を表示します。

　・ステータス表示１
　　　エラーが発生したり、録画中などの現在の状態を表示することがありま
　　　す。

　・ステータス表示２
　　　Signal、ドロップ、スクランブル、UDP送信先などのステータスを表示
　　　します。

■設定■
　●基本設定タブ
　　※設定値はEpgTimer.exeと共通となります。
　　・設定関係保存フォルダ
　　　　チャンネル設定やEPGデータなどを保存するフォルダを指定します。

　　・録画保存フォルダ
　　　　即時録画時と予約録画時にファイルを保存するフォルダを指定します。
　　　　複数登録することで、空きがなくなった場合のサブ録画フォルダを指
　　　　定できます。
　　　　◆「追加」を押してリストに追加しないと有効になりません。

　●動作設定タブ
　　・全サービスを処理対象とする
　　　　複数のサービスから構成されているチャンネルは、全サービスを処理
　　　　対象とします。
　　　　チェックがOFFの場合、指定サービスモード（指定サービスのデータの
　　　　み処理する）となります。
　　　　予約録画の場合はEpgTimer.exeの録画モードによって変化します。

　　・スクランブル解除処理を行う
　　　　スクランブル解除モジュール（B25Decoder.dllなど）を使用します。
　　　　BonDriverで解除される場合はOFFにすると、余分な処理が省けます。

　　・EMM処理を行う
　　　　スクランブル解除時にEMMの処理を行います。
　　　　動作はスクランブル解除モジュール（B25Decoder.dllなど）に依存し
　　　　ます。

　　・字幕データを含める
　　　　指定サービスのみの場合、デフォルトでは字幕データは処理対象には
　　　　入らないため、処理対象に入れます。
　　　　予約録画の場合、録画設定によって変化します。

　　・データ放送のデータを含める
　　　　指定サービスのみの場合、デフォルトではデータ放送のデータは処理
　　　　対象には入らないため、処理対象に入れます。
　　　　予約録画の場合、録画設定によって変化します。

　　・録画ファイル名が同一の場合に上書きする
　　　　録画ファイル名が同一になった場合に上書きします。
　　　　OFFの場合は-(1)などがファイル名につきます。

　　・視聴中にEPGデータの取得を行う
　　　　EPG取得設定でEPGデータの取得対象になっているサービスを視聴した
　　　　場合、自動的にEPGデータを取得します。

　　・録画中にEPGデータの取得を行う
　　　　EPG取得設定でEPGデータの取得対象になっているサービスを録画した
　　　　場合、自動的にEPGデータを取得します。

　　・Ch切換、録画開始？秒後から取得する
　　　　視聴中、録画中に自動取得するEPGデータの開始タイミングを指定します。

　　・最小化時にタスクトレイに入れる
　　　　最小化したときにタスクトレイに入れます。

　　・次回起動時に終了前のサービスで起動する
　　　　次回起動時に終了前のBonDriverとサービスが選択された状態で起動し
　　　　ます。

　●EPG取得設定タブ
　　※設定値はEpgTimer.exeと共通となります。
　　・EPG取得対象サービス
　　　　EPG取得を行うサービスにチェックを入れます。同一物理チャンネルで
　　　　チェックの入っているものと入っていないものがある場合、入ってい
　　　　ない方のサービスも一緒に取得されます。

　　・全チェック ボタン
　　　　全てのサービスにチェックを入れます。

　　・映像サービスのみチェック ボタン
　　　　映像サービスのみチェックを入れます。データ放送のみ（ワンセグサー
　　　　ビス含む）のサービスはチェックが解除されます。

　　・全クリア
　　　　全てのサービスのチェックをクリアします。

　　・基本情報のみ取得するネットワーク
　　　　BS/CS1/CS2で１チャンネルから全チャンネルの基本情報のみ取得しま
　　　　す。番組詳細は指定サービスの物理チャンネルのもののみ取得されま
　　　　す。どうしても番組詳細が必要な場合を除いてチェックを入れること
　　　　をお勧めします。番組詳細まで全チャンネル取得するには、長時間か
　　　　かります。

　●サービス表示設定タブ
　　・BonDriver
　　　　サービス表示を設定するBonDriverを選択します。

　　・表示サービス
　　　　サービスの一覧に表示するサービスにチェックを入れます。

　　・全チェック ボタン
　　　　全てのサービスにチェックを入れます。

　　・映像サービスのみチェック ボタン
　　　　映像サービスのみチェックを入れます。データ放送のみ（ワンセグサー
　　　　ビス含む）のサービスはチェックが解除されます。

　　・全クリア ボタン
　　　　全てのサービスのチェックをクリアします。

　　・削除 ボタン
　　　　項目を削除します。一度削除すると再度チャンネルスキャンを行うま
　　　　で表示されません。
　　　　県境などで、同じチャンネルがある場合に、受信環境の悪い方を削除
　　　　する場合などに使用してください。

　●ネットワーク設定タブ
　　・UDP送信
　　　　設定したIPのポートにMPEG2-TSのデータをUDPで送信します。
　　　　EpgDataCap_Bonが複数起動されている場合は、自動的にポートが+1さ
　　　　れます。
　　　　ブロードキャストとして処理する場合は、サブネットマスクによって
　　　　適切なIPを指定してください。
　　　・送信時のWait
　　　　　UDP送信を1度行った後のWaitを指定します。
　　　　　うまく再生されないときに変更すると改善される場合があります。
　　　・一度に送信する最大パケット数
　　　　　UDP送信で1度に送るTSパケットの数を指定します。
　　　　　うまく再生されないときに変更すると改善される場合があります。

　　・TCP送信
　　　　設定したIPのポートにMPEG2-TSのデータをTCPで送信します。
　　　　EpgDataCap_Bonが複数起動されている場合は、自動的にポートが+1さ
　　　　れます。
　　　　受信側はBonDriver_TCP.dllを使用する必要があります。

　●外部アプリケーション設定タブ
　　Viewボタン
　　　Viewボタンで起動する外部アプリケーションの設定を行います。
　　　使用しない場合は特に設定する必要ありません。
　　　・Viewで使用するexeへのパス
　　　　UDPやTCPで動画再生できるアプリ（TVTestなど）へのパスを指定して
　　　　ください。

　　　・View起動時のコマンドラインオプション
　　　　UDPで動画再生できるアプリを起動するときのコマンドラインオプショ
　　　　ンを設定します。


■Q&A■
・UDPでうまく再生されない
＝＞パケット送信時のWaitと一度に送信するTSパケット数をいろいろ変えて試
　　してください。ネットワーク環境によって最適な値が変わります。
　　無線LANの場合は帯域が足りなくて再生できないことがあります。
　　UDPではなくTCPを使用すると安定することもあります。

・「B25Decoder.dllの読み込みに失敗しました」と出るんだけど
＝＞必要なランタイムがインストールされていない可能性があります。
　　VC++ 2005 SP1 再頒布可能パッケージなどをインストールしてみてください。
　　カードリーダーが接続されていな可能性もあります。

・EPGデータが取得できない
＝＞ドロップの大量に発生するチャンネルでは正常に取得できません。
　　放送休止中はEPGデータを配信していない場合もあります。
　　ワンセグは数時間分しか送信されていないので1週間分はありません。
　　フルセグとは異なるのでワンセグのみのTSデータから取得することはでき
　　ません。（蓄積判定ができません）

・Friioの新白で動かない
＝＞人柱版９．xxの「新」フォルダにあるBonDriverを「BonDriver」フォルダ
　　にあるモジュールを使用してください。
　　Meru氏のカスタム版を使用する必要があります。

・亀は？
＝＞IBonDriver2 インターフェースが組み込まれているユニデン用のBonDriver
　　が別途公開されています。そちらを導入してください。

・B25の処理をさせたくないんだけど
＝＞B25Decoder.dllを削除してください。削除しても動作します。

・ネットワークリモコンは？
＝＞需要はないと判断したため削除しました。EpgTimerのNetWorkTVモードを
　　使用してください。

・「BonDeiverのオープンができませんでした」と出る
＝＞OSがチューナーが認識していない、別のアプリで使用中などが考えられます。
　　64bit環境で32bitモジュールを使用している（または逆）の可能性もあり
　　ます。

・使用メモリが増えていくんだけど
＝＞BonDriver側がメモリリークを起こしている。
　　処理が追いつかなくて処理バッファが貯まっている。
　　EPGデータの蓄積による増加。
　　OSがメモリに余裕あるのでキャッシュとして保持している。
　　などが考えられます。

・スクランブルが解除できない
＝＞B25Decoder.dllの同梱をやめましたので、別途どこからか手に入れてください。

★以下わかる人用★
■ネットワーク毎にスクランブル解除モジュールを変更する■
　B25Decoder.dll以外のスクランブル解除モジュールを使用したい場合、
　ネットワーク毎に使用モジュールを変更することが可能です。
　使用モジュールはB25Decoder.dllのインターフェースと同一の必要があります。
　BonCtrl.iniにて指定可能です。
　以下の書式で追加してください
　（OriginalNetworkID 16進数4桁）（TransportStreamID 16進数4桁）=ファイル名
　FFFFを指定することでデフォルト値を指定可能です。
　例：
　　0004FFFF=B25Decoder.dll
　　00040001=B25Decoder2.dll

　　OriginalNetworkID 0x0004はデフォルトB25Decoder.dllで解除
　　OriginalNetworkID 0x0004 TransportStreamID 0x0001はB25Decoder2.dllで解除

■強制的に起動時のBonDriverとサービス指定を行う■
　この設定はEpgDataCap_Bon.exeを単独で起動したときのみ、有効な設定にな
　ります。予約録画時などは無視されます。
　動作設定で「次回起動時に終了前のサービスで起動する」のチェックがOFFの
　場合、EpgDataCap_Bon.iniのSETに以下のものを追加することで起動時の
　BonDriverとサービスを指定できます。
　　OpenFix：1で機能を有効、0で機能を無効
　　FixBon：BonDriverのファイル名（拡張子含む）
　　FixONID：OriginalNetworkIDの10進数
　　FixTSID：TransportStreamIDの10進数
　　FixSID：ServiceIDの10進数

■TSデータのバッファリング最大値を変更する■
　TSデータのバッファリング最大値を設定します。
　設定値はBonDriverからのTSデータ取得を何回バッファリングするかになります。
　Byte単位でのバッファサイズは使用BonDriverによって変化します。
　（例：BonDriver_PT-STの場合、1回で取得するTSデータは 188*256=48128バイト）
　EpgDataCap_Bon.iniのSETにTsBuffMaxCountを追加すること設定可能。
　（デフォルト:5000）

■ファイル出力データのバッファリング最大値を変更する■
　ファイル出力データのバッファリング最大値を設定します。
　設定値は出力予定のTSデータを何回バッファリングするかになります。
　Byte単位でのバッファサイズは使用BonDriver、指定サービスでの出力かによって変化します。
　（最大値は使用BonDriverで1回で取得するTSデータのサイズ）
　EpgDataCap_Bon.iniのSETにWriteBuffMaxCountを追加すること設定可能。
　-1で最大値無限
　（デフォルト:-1）

　ファイル出力データのバッファリングで最大値に達した場合、エラーログや録画結果の
　ドロップ数にカウントされません。
　エラーログなどの数値はファイル出力処理を行う前までのTSデータに対しての数値にな
　ります。

■予約録画時に強制的に起動時のサービス指定を行う■
　この設定はEpgDataCap_Bon.exeが予約録画用に起動したときのみ、有効な設定にな
　ります。
　EpgDataCap_Bon.iniにBonDriverのファイル名（拡張子含む）のセクションを追加し、
　以下のものを追加することで起動時のサービスを指定できます。
　　OpenFix：1で機能を有効、0で機能を無効
　　FixONID：OriginalNetworkIDの10進数（デフォルト値:-1）
　　FixTSID：TransportStreamIDの10進数（デフォルト値:-1）
　　FixSID：ServiceIDの10進数（デフォルト値:-1）
　　OpenWait：チューナーオープン後のWait(msec単位)（デフォルト値:0）
　　ChgWait：チャンネル切換後のWait(msec単位)（デフォルト値:0）

■EPG取得のタイムアウト値を変更する■
　EPG取得時に蓄積判定を行えない場合に、タイムアウトするまでの時間を変更します。
　BonCtrl.iniのEPGCAPにEpgCapTimeOutを追加すること設定可能。
　　EpgCapTimeOut:10進数で分数（デフォルト:10）

■EPG取得でタイムアウト発生時にファイルを保存する■
　EPG取得時に蓄積判定を行えずタイムアウトした場合は、異常としてEPGデータの保存を行いません。
　BonCtrl.iniのEPGCAPにEpgCapSaveTimeOutを追加すること設定可能。
　　EpgCapSaveTimeOut: 0:保存しない、1:保存する

■チャンネルスキャンのタイムアウト値を変更する■
　チャンネルスキャン時のタイムアウト値を変更します。
　BonCtrl.iniのCHSCANにChChgTimeOutとServiceChkTimeOutを追加すること設定可能。
　　ChChgTimeOut：有効なTSデータが流れてくるまでのチェック秒数（デフォルト:9）
　　ServiceChkTimeOut：サービスの一覧を確認できるまでのチェック秒数（デフォルト:8）

■BonDriverオープン後にwaitを入れる■
　BonDriverオープン後にwaitを入れます。
　BonDriverオープン後にすぐにチャンネル切換処理をすると、正常に切り替わらない
　場合のある環境で試してみてください。
　EpgDataCap_Bon.iniのSETにOpenWaitを追加すること設定可能。
　　OpenWait：10進数でmsec（デフォルト：200）

