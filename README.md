# 教員が新しい GitHub Pages サイトを作るときのテンプレート

## 初期設定作業

1. （教員）GitHub アカウントを取得

1. （脇田）

    1. [y18チームに招待](https://github.com/orgs/titechcomp/teams/y18/members)

    1. 新しいリポジトリを作成し，このリポジトリを clone したものをプッシュ

    1. [y18のリポジトリ](https://github.com/orgs/titechcomp/teams/y18/repositories)に新しいリポジトリを追加

    1. リポジトリ設定を変更: `GitHub Pages := master branch / docs folder`

    1. リポジトリの所有権を申請した教員に譲渡

    1. [情報リテラシ第一](https://titechcomp.github.io/y18-il1j/)，[情報リテラシ第二](https://titechcomp.github.io/y18-il2j/)のページにリンクを追加

1. （教員）`docs` ディレクトリに保存されたが GitHub Pages として公開される．公開ページはGitHub のコードページではなく，Settings ページに指定された URL となることに注意して下さい．

## 編集作業

`docs/` 以下に HTML ファイル等を保存し，GitHub にコミットすれば公開されます．

GitHub へのプッシュから数秒後に GitHub Pages で閲覧できるようになります．でも，既存のファイルを更新しプッシュしても，新しい版が表示されないことがしばしばあります．これは，GitHub のウェブコンテンツを配信している CDN (Content Delivery Network) のキャッシュの影響です．しばらく放置しておけば，見られるようになるはずですが，すぐに見たい場合は URL に無駄な Query 文字列を追加すればすぐに見られます．

`https://titechcomp.github.io/empty-project/?3.141592653`

自己サイト内のページの参照にはリポジトリ名からの相対パス名を利用するとよいでしょう（例: `/empty-project/day1/page12.html`）．もちろん，相対パスも利用できます．

ページの構成方法については[既存のウェブサイト群](https://github.com/titechcomp)のソースコードの`docs`ディレクトリのファイルが参考になるでしょう．

## Jekyll か HTML か

GitHub Pages が本来，提供している機能は Jekyll と呼ばれる Markdown を用いた静的HTMLウェブサイト生成システムです．Jekyll を利用する場合は `docs` には HTML ではなく Markdown ファイルを配置して下さい．プッシュする時点で Jekyll が Markdown 記述を HTML に変換したものが GitHub Pages に公開されるようです．`docs/.nojekyll` はこの機能を抑制し，HTML を自分で記述する目的で配置したものです．Jekyll を利用したい場合は，このファイルを削除して下さい．

## Links

- [y18チームメンバー](https://github.com/orgs/titechcomp/teams/y18/members)

- [y18のリポジトリ](https://github.com/orgs/titechcomp/teams/y18/repositories)

- [Discussion](https://github.com/orgs/titechcomp/teams/y18)
