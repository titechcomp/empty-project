# 教員が新しい GitHub Pages サイトを作るときのテンプレート

## 初期設定作業

1. （教員）GitHub アカウントを取得し、脇田に GitHub アカウントを通知して下さい。

1. （脇田）

    1. [y18チームに招待](https://github.com/orgs/titechcomp/teams/y18/members)

    1. 新しいリポジトリを作成し，このリポジトリを clone したものをプッシュ

    1. [y18のリポジトリ](https://github.com/orgs/titechcomp/teams/y18/repositories)に新しいリポジトリを追加

    1. リポジトリ設定を変更: `GitHub Pages := master branch / docs folder`

    1. リポジトリの所有権を申請した教員に譲渡

    1. [情報リテラシ第一](https://titechcomp.github.io/y18-il1j/)，[情報リテラシ第二](https://titechcomp.github.io/y18-il2j/)のページにリンクを追加

1. （教員）`docs` ディレクトリに保存された内容が GitHub Pages として公開されます．公開ページはGitHub のコードページではなく，Settings ページに指定された URL となることに注意して下さい．

    たとえば，このリポジトリの URL は `https://github.com/titechcomp/empty-project/` ですが，このページを公開したウェブサイトの URL は `https://titechcomp.github.io/empty-project/` です．

## 編集作業

`docs/` 以下に HTML ファイル等を保存し，GitHub にコミットすれば公開されます．

GitHub へのプッシュから数秒後に GitHub Pages で閲覧できるようになります．でも，既存のファイルを更新しプッシュしても，新しい版が表示されないことがしばしばあります．これは，GitHub のウェブコンテンツを配信している CDN (Content Delivery Network) のキャッシュの影響です．しばらく放置しておけば，見られるようになるはずですが，すぐに見たい場合は URL に無駄な Query 文字列を追加すればすぐに見られます．

`https://titechcomp.github.io/empty-project/?hoge`

自己サイト内のページの参照にはリポジトリ名からの絶対パス名を利用するのが便利でしょう（例: `/empty-project/day1/page12.html`）．もちろん，相対パスも利用できます．

ページの構成方法については[既存のウェブサイト群](https://github.com/titechcomp)のソースコードの`docs`ディレクトリのファイルが参考になるでしょう．

## 編集内容のテスト

Git add/commit/push して、GitHub の様子を観察することもできますが、時間と手間がかかるので大変です。手元の環境で確認するのが手っ取り早いのですが、ちゃんとしたサーバでないとリンク先は読み込んでいるJavaScriptが正常に動作しないなどの問題が起きやすいです。

一番のお勧めは、手元のパソコンでウェブサーバを起動することで。でも、Apache をインストールして設定するのは面倒。たしかに、それは面倒。でも、もっと簡便な方法があるんです。それは PHP をはじめとするスクリプト言語の組込み機能のHTTPサーバを利用することです。

macOS の場合、元々、PHP が利用できるのでウェブサイトのディレクトリに `cd` し、 `php --server localhost:8080 --docroot .` するだけでサーバを起動できます。みなさんの便利のために `bin/server` としてこのスクリプトを保存しておきました。PHP が利用できない場合は、[ほかのスクリプト言語を使って簡単にできる](https://qiita.com/sudahiroshi/items/e74d61d939f18779970d)ようです。

## Jekyll か HTML か

GitHub Pages が本来，提供している機能は Jekyll と呼ばれる Markdown を用いた静的HTMLウェブサイト生成システムです．Jekyll を利用する場合は `docs` には HTML ではなく Markdown ファイルを配置して下さい．プッシュする時点で Jekyll が Markdown 記述を HTML に変換したものが GitHub Pages に公開されるようです．`docs/.nojekyll` はこの機能を抑制し，HTML を自分で記述する目的で配置したものです．Jekyll を利用したい場合は，このファイルを削除して下さい．

## Links

- [y18チームメンバー](https://github.com/orgs/titechcomp/teams/y18/members)

- [y18のリポジトリ](https://github.com/orgs/titechcomp/teams/y18/repositories)

- [Discussion](https://github.com/orgs/titechcomp/teams/y18)
