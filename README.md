# エクササイズ

ページ切り替えができる掲示板アプリを作る

(Vue編の「【エクササイズ】掲示板アプリを作る」で作成したアプリに機能追加をする形)

## ステップ1. Vue Routerの追加と、それに伴う不要ファイルの削除と一部ファイルの修正を行う

1. 完成形の動作確認(これから実装するアプリのイメージを把握する)
1. Vue編の「【エクササイズ】掲示板アプリを作る」のコードをgit cloneして前回課題の完成形をダウンロードする
    - もしくは自分で作成したアプリを使うのであれば、git cloneの必要は無し
1. Vue Routerを追加する
1. Vue Routerを追加した際の不要ファイルの削除とコード一部修正

---

## ステップ2. 「ページ別のコンポーネント作成」、「ルーティングの設定」、「router-link, router-viewの埋め込み」を行う

以下3つのコンポーネント作成を行う。

1. 3ページ分のコンポーネントファイルを作成する(src/viewsディレクトリの中)
    - 全体連絡 : General.vue
    - 雑談 : Chat.vue
    - 自己紹介 : SelfIntroduction.vue
1. ルーティングの設定をする(src/router/index.js)
    - 作成した3つのコンポーネントをセットする
    - 今回のpath設定
      - /                  : Generalコンポーネント
      - /chat              : Chatコンポーネント
      - /self-introduction : SelfIntroductionコンポーネント
1. App.vueの修正
    - Main.vueのstyleを持ってくる
    - Mainコンポーネントを埋め込んでたところに「router-view」を埋め込む
1. SideMenu.vueに「router-link」を使ってページ遷移行えるようにする
    - v-forで実装できるように、リンク作成に必要な情報を配列で用意する
    - styleの調整

---

## ステップ3. 「Main.vueの名前変更」と「3つのページコンポーネントの具体的な実装」を行う

1. 「Main.vue → MessageView.vue」に名前を変更する
1. 作成した3つのページコンポーネント内に「MessageView.vue」を埋め込む
1. 「MessageView.vue」のコードを一部修正する
1. ページを切り替える毎にデータが消える問題を解決する
  - Vueの機能「keep-alive」を使う
      - ページ切替時にコンポーネントを削除せずにキャッシュに残しておく(裏側で状態を保持しておく)
      - 参考ドキュメント
          - https://jp.vuejs.org/v2/guide/components-dynamic-async.html
          - https://router.vuejs.org/ja/api/#router-view
