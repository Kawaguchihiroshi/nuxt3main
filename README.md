# Nuxt3プロジェクト環境構築手順　
以下、内容の環境を作成する。
```
"volta": 1.1.1
"Node": v20.11.1 (default)
"npm": v10.5.0 (default)
"pnpm": 8.15.5
"nuxt": "^3.11.1"
"prettier": "^3.2.5"
"vuetify-nuxt-module": "^0.12.0"
"@vueuse/nuxt": "^10.9.0"
"pinia": "^2.1.7"
```
## 開発環境の構築手順
### 【volta】:Nodeのバージョン管理ツール
###### 確認方法
```
$ volta -v
```
（想定結果）1.1.1<br>
#### インストール手順
１，こちらにアクセス　https://docs.volta.sh/guide/getting-started<br>
２，「For Windows, download and run the Windows installer and follow the instructions.」のリンク部分からインストーラーをダウンロード<br>
３、インストール<br>
<br>
◆開発者モードにしないと動かない？<br>
https://zenn.dev/nawomat/articles/26ea129dcda8a7<br>
◆win11開発者モードに変更する手順<br>
https://pc-karuma.net/enable-developer-mode-windows-11/<br>
<br><br>
### 【Node】：環境
###### 確認方法
```
$ node -v
```
（想定結果）20.11.1
###### 変更方法
```
$ volta install node@20.11.1
```
（成功結果）success: installed and set node@20.11.1 (with npm@10.2.4) as default<br>
<br><br>
### 【npm】：パッケージマネージャー
###### 確認方法
```
$ npm -v
```
（想定結果）10.5.0
###### 変更方法
```
$ volta install npm@10.5.0
```
（成功結果）success: installed and set npm@10.5.0 as default<br>
<br><br>
### 【pnpm】：パッケージマネージャー
###### 確認方法
```
$ pnpm -v
```
（想定結果）8.15.5
###### インストールコマンド
```
$ iwr https://get.pnpm.io/install.ps1 -useb | iex
```
<br><br><br>
### 【nuxt】：Vueフレームワーク
###### 確認方法
package.jsonファイル内で確認<br>
（想定結果）3.11.1
###### インストールコマンド
```
$ pnpm dlx nuxi@latest init
```
###### コマンド結果
```
Packages: +1
+
Progress: resolved 2, reused 0, downloaded 1, added 1, done

✔ Which package manager would you like to use?
pnpm
◐ Installing dependencies...                                                                                                           14:35:11  
Packages: +754
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Progress: resolved 802, reused 621, downloaded 133, added 754, done
node_modules/.pnpm/vue-demi@0.14.7_vue@3.4.21/node_modules/vue-demi: Running postinstall script, done in 4s

> nuxt-app@ postinstall C:\project\nuxt3-main\nuxt-app
> nuxt prepare

ℹ Compiled plugins/server.mjs in 594.05ms                                                                                             14:38:08
ℹ Compiled plugins/client.mjs in 638.7ms                                                                                              14:38:08
ℹ Compiled types/plugins.d.ts in 639.77ms                                                                                             14:38:08
✔ Types generated in .nuxt                                                                                                            14:38:08   

dependencies:
+ nuxt 3.11.1
+ vue 3.4.21
+ vue-router 4.3.0

Done in 2m 45.9s
✔ Installation completed.                                                                                                             14:38:08   

✔ Initialize git repository?
Yes
ℹ Initializing git repository...                                                                                                      14:38:54   

Initialized empty Git repository in C:/project/nuxt3-main/nuxt-app/.git/
                                                                                                                                       14:38:54  
✨ Nuxt project has been created with the v3 template. Next steps:
 › cd nuxt-app                                                                                                                         14:38:54  
 › Start development server with pnpm run dev                                                                                          14:38:54
```
###### インストールコマンド
```
$ cd nuxt-app
$ pnpm install
```
###### コマンド結果
```
Lockfile is up to date, resolution step is skipped
Already up to date

> nuxt-app@ postinstall C:\project\nuxt3-main\nuxt-app
> nuxt prepare

✔ Types generated in .nuxt                                                                                                            14:41:31   
Done in 4.4s
```
<br><br><br>
#### 【vuetify-nuxt-module　0.12.0】：Nuxt用のVuetifyモジュール　https://nuxt.com/modules/vuetify-nuxt-module
最新は0.13.1（4/1時点）
```
pnpm add vuetify-nuxt-module -D
```
#### 【vueuse　10.9.0】：use〇〇が使えるようになる便利ツール　https://vueuse.org/
```
pnpm i @vueuse/core
```
#### 【pinia　2.1.7】：状態管理ツール　https://pinia.vuejs.org/
```
pnpm install pinia
```
#### 【prettier 3.2.5】：フォーマッター　https://prettier.io/
```
pnpm add --save-dev --save-exact prettier
```
###### 全てのファイルのフォーマットをそろえる
```
pnpm exec prettier . --write
```
###### vscordでファイル保存時にフォーマットを書ける方法

<br><br><br><br>
## 【注意事項】
VSCodeは常に最新にしておくこと
<br><br><br><br>

## 【備考】
今後必要になりそうなライブラリ
#### 【aws-amplify/cli】：https://aws.amazon.com/jp/getting-started/guides/deploy-webapp-amplify/module-one/
```
pnpm install -g @aws-amplify/cli
```
