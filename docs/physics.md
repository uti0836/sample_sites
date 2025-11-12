# 物理
## ① 自由落下
物体が重力に引かれ、**初速度0.0[m/s]**で**鉛直下向き**に落下する運動を、自由落下といいます。等加速度運動のバリエーションのうち、最も簡単な運動です。「自由落下」「シミュレーション」で検索すれば、個人的にシミュレーションをつくっておられる方もたくさん見つかります。

<!--
ボタンに色を塗りたい場合、.md-button--primaryを追加する
[自由落下シミュレーション :fontawesome-brands-windows:](https://okiraku-lab.github.io/freefall/freefall.html){:target="_blank" .md-button .md-button--primary }
-->
[自由落下シミュレーション :fontawesome-brands-windows:](https://okiraku-lab.github.io/freefall/freefall.html){:target="_blank" .md-button }
![](./image/自由落下_1.png)
!!!note "アプリの使い方"
	- ボールを落とす「高さ」を入力し、🔛マークをクリックすると、シミュレーションが始まります
	- 🔙マークをクリックすると、シミュレーションをリセットできます

## ② 鉛直投げ上げ
物体を鉛直方向に投げ上げることを、鉛直投げ上げといいます。高校物理では、等加速度運動の1つのバリエーションとして、自由落下と同じタイミングで学習します。自由落下も鉛直投げ上げも、**本質的には加速度 a≒9.8[m/s²] の等加速度運動**ですが、物理という科目に慣れるまでは、なかなかそのへんの関連性に気づかないと思います。ただ、いったん同じように考えられることに気づけば、物理という科目がぐっと面白くなります。

[鉛直投げ上げシミュレーション :fontawesome-brands-windows:](https://okiraku-lab.github.io/throwingup/throwingup.html){:target="_blank" .md-button }
![](./image/鉛直投げ上げ_1.png)
!!!note "アプリの使い方"
	- ボールを投げ上げる「高さ」と「初速度」を入力し、🔛マークをクリックすれば、シミュレーションが始まります
	- 🔙マークをクリックすると、シミュレーションをリセットできます

## ③ 斜方投射シミュレーション（解析解）
物体に斜めに、一定の角度をつけて投げ出すことを斜方投射といいます。斜方投射では、投射角度の範囲は0＜θ＜90です（※θが0度なら水平投射、90度なら鉛直投げ上げになります）。物体が斜めに動くことから、複雑な運動のように感じますが、**初速度を水平方向と鉛直方向に分解すれば**、物体の動きを予測することは容易です。

シミュレーションは、解析解を求める手法と数値解を求める手法の二通りで再現しました。このWebアプリは、物体の位置を解析的に求めるというものです。

[斜方投射シミュレーション（解析解） :fontawesome-brands-windows:](https://okiraku-lab.github.io/projectilemotion_type1/projectilemotion_type1.html){:target="_blank" .md-button }
![](./image/斜方投射（解析解）_1.png)
!!!note "アプリの使い方"
	- 「初速度」と「投射角」を入力し、🔛マークをクリックすれば、シミュレーションが始まります
	- 🔙マークをクリックすると、シミュレーションをリセットできます
数年ほど前に、本Webアプリのプロトタイプに当たるデスクトップアプリをつくりました。以下の動画は、そのデスクトップアプリを使って、斜方投射の考え方を説明したものです。過去のコンテンツ故、ビジュアル表現が稚拙ですが、現象の理解にお役立てください。

| 斜方投射（前編）・シミュレーションで現象解説 | 斜方投射（後編）・シミュレーションで現象解説 |
| :---: | :---: |
| <iframe src="https://www.youtube-nocookie.com/embed/jNZqkx9LIEM?si=9zyiRrFK6tTDEBvp" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe> | <iframe src="https://www.youtube-nocookie.com/embed/JSkbkGPn310?si=U4-OGxHfceHKn8MP" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe> |

## ④ 斜方投射シミュレーション（数値解）
本シミュレーションでは、プログラム内の1ループごとに少しずつ時間を進め、ボールの速度を変化させ、移動距離を割り出します。つまり、逐次的な計算を行い、ボールの位置を求めます。逐次的とは、1つ前の計算結果から、次の計算結果を得るということです。具体的にいうと、プログラム内の1ループごとに、加速度ベクトルをもとに速度ベクトルを変化させ、速度ベクトルをもとに位置ベクトルを求めます。加速度ベクトルの大きさは一定ですが、速度ベクトルと位置ベクトルは刻一刻と移り変わり、ボールの動きは変化します。これを、**オイラー法**といいます。

少しずつ時間を進めるときの刻み間隔（Δt）は、10ミリ秒としています。Δtの値を細かく刻むほど、精度の高い計算結果が得られますが、時間を無限に細かく刻むことは不可能であり、ボールの挙動には必ず誤差が生じます。

[斜方投射シミュレーション（数値解） :fontawesome-brands-windows:](https://okiraku-lab.github.io/projectilemotion_type2/projectilemotion_type2.html){:target="_blank" .md-button }
![](./image/斜方投射（数値解）_1.png)
!!!note "アプリの使い方"
	- 「初速度」と「投射角」を入力し、🔛マークをクリックすれば、シミュレーションが始まります
	- 🔙マークをクリックすると、シミュレーションをリセットできます
	- 「はね返り係数」のスライダーを動かすと、反発係数：eを0～0.7の範囲で変えることができます
ゲームなどのバーチャル世界で、ボールに本物っぽい動きをさせたい場合、ボールに働いている力を考え、運動方程式：ma=Fを立てて、加速度aを求めて、オイラー法やルンゲ・クッタ法などのアルゴリズムを適応すれば、時間に制限されない制御が可能です。