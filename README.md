# TodoApp

## このプロジェクトでやりたいこと

- Kotlinを使用したTodoAppの作成をしたい
- qiitaの記事を参考にする

## 使用する資料

- [作るアプリの工程](https://qiita.com/Nabe_LiT/items/660e97150fb87a2e7ffd)
- [公式ドキュメント](https://firebase.google.com/docs/auth/android/firebaseui?hl=ja)

## 資料と異なるところ

- [Androidサポートライブラリ](#androidサポートライブラリ)
- [言語](#言語)
- [ライブラリのバージョン](#ライブラリのバージョン)

### Androidサポートライブラリ

com.android.support:supportとandroidx
androidxが後継ライブラリでこれによる他のライブラリとの相性はわからない

### 言語

KotlinとJava
書き方は違うが、ファイルは混在させることができて、いまのところ影響はない

### ライブラリのバージョン

Qiitaの古い記事や新しい公式ドキュメントから引用したコードが混在していて、これをもとに問題が発生するかもしれないのでライブラリのバージョン自体は公式サイトに合わせる

## 用語

### プラグイン

特定の機能やタスクを提供し、プロジェクトのビルドプロセスに対して影響を与えるもの


## 作業ログ

> ~1/29 
> Chapter3まで完了

> 1/30
> Chapter4の途中まで
> 作業ログをREADME.mdに記載することにした
> 使用するライブラリの競合が発生し、解決しなかった

> 1/31
> 前回のエラー解決
> - Qiitaで書かれていた、com.firebaseui:firebase-ui-authの指定されていたバージョンが使えない
> - 7.2.0にしたら解決した
> - androidx.activity:activity:1.8.2を使うには、Android APIs 34以上が必要
> - 34にアップデートしたら同期はできたがclean projectからのrebuild projectでエラーが発生した
>   - Duplicate class com.google.android.gms.internal.measurement.zzu found in modules firebase-analytics-impl-16.2.4-runtime 
>   - それぞれのライブラリがどこで指定されているのか不明
> - 使用するライブラリを見直すことにした。成るべく公式サイトに合わせることにした
> - com.firebaseui:firebase-ui-authのバージョンは公式ドキュメントのものに変更してerrorはなくなった
> - com.google.firebase:firebase-authをkotlin専用のライブラリのcom.google.firebase:firebase-auth-ktxに変更した
> - build.gradle.ktsで指定しているNamespaceが認識されなくなった意味わからん
> - firebase-bomの使用をやめたら解決したなんでかはわからんけどなにかのライブラリと重複してたのかな
