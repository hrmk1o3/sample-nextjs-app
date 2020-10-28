# Next.js の使用感

## react-app と next-app の互換性

routing まわりの書き方が異なるので多少移植の手間がかかるが、コンポーネントは基本的に使いまわせる。
試していないが、おそらく Redux も使いまわせる。

## Typescript 対応

すぐに出来た。
しかし、 Next.js がデフォルトで利用している CSS Modules との相性が悪そう。
[このあたり](https://github.com/mrmckeb/typescript-plugin-css-modules#visual-studio-code)を参考にしてみたものの、
index.tsx で Home.module.css を読み込むところで警告が出る。

## tailwind 対応

create-next-app のオプションで指定できるテンプレートが用意されている。

```sh
npx create-next-app --example with-tailwindcss with-tailwindcss-app
```

まだ調査できていないが、VSCode の `@tailwind` が認識できないという警告が出る。

## API

簡単な API を実装できる。
がっつりとデータベースを用意して動かすような用途を想定しているかはわからない。
外部のデータベースを見に行ってデータを加工してから React 側に渡してあげられるといった使い方が想定される。
機密情報を含めてデプロイしてよいかなど、セキュリティ面に関しては要確認。
