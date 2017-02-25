# [Gamemakin](https://gamemak.in) UE4スタイルガイド() {

*Unreal Engine 4 への最も合理的なアプローチ*

[Airbnb Javascript Style Guide](https://github.com/airbnb/javascript) に大きな影響を受けています。

[![Analytics](https://ga-beacon.appspot.com/UA-80567399-1/repo?useReferrer)](#) ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

## Unreal Engine 4 Linter Plugin

このスタイルガイドに対してプロジェクトをチェックする自動化された方法は、[the Unreal Engine marketplace](https://www.unrealengine.com/marketplace/linter) で購入できます。 このプラグインのソースコードは最終的に無料になりますが、ソースコードからエンジンをビルドせずにUE4で使用するには、マーケットプレイス版を使用してください。

## このスタイルガイドを検討する 

Gamemakin LLCは、Discordの http://discord.gamemak.in にpublicチャンネルを持っており、スタイルガイドとLinterプラグインに関するあらゆる事について、議論したい場合は #linter チャンネルを使用してください。 

## 本ドキュメントへリンクする場合

このスタイルガイドの各セクションは、簡単な参照と簡単なリンクのために番号が付けられています。 http://ue4.style の最後にハッシュタグとセクション番号を付加するだけで、任意のセクションに直接リンクすることができます
たとえば、このスタイルガイドの第1原則に誰かを送りたい場合は、 http://ue4.style#0.1 という結果になる `＃0.1` を追加します。

## フォークと翻訳

このレポへのプルリクエストに適していない注目すべきフォークまたは翻訳を行った場合は、ここにフォークまたは翻訳を追加するプルリクエストを提出してください。

* [Korean Translation](https://github.com/ymkim50/ue4-style-guide/blob/master/README_Kor.md) by ymkim50
* [Russian Translation](https://github.com/CosmoMyzrailGorynych/ue4-style-guide-rus/blob/master/README.md) by CosmoMyzrailGorynych
* [Japanese Translation](https://github.com/akenatsu/ue4-style-guide/blob/master/README.jp.md) by akenatsu
* [Chinese Translation](https://github.com/skylens-inc/ue4-style-guide/blob/master/README.md) by Beijing Skylens Tech.

## 重要用語

<a name="terms-level-map"></a>
##### Levels/Maps

'map' という語は一般に、平均的な人が 'level' と呼んでいるものを指し、互換的に使用することができます。この用語の歴史については[こちら](https://en.wikipedia.org/wiki/Level_(video_gaming))を参照してください。

<a name="terms-cases"></a>
##### 記法(Cases)

物事に名前を付ける方法はいくつかあります。 ここに一般的ないくつかの記法の種類があります:

> ###### PascalCase
>
> すべての単語を大文字にし、スペースをすべて削除します。例： `DesertEagle`, `StyleGuide`, `ASeriesOfWords`.
> 
> ###### camelCase
>
> 最初の文字は常に小文字ですが、その後のすべての単語は大文字で始まります。例： `desertEagle`, `styleGuide`, `aSeriesOfWords`.
>
> ###### Snake_case
>
> 単語は任意に大文字または小文字を開始できますが、単語はアンダースコアで区切られます。例： `desert_Eagle`, `Style_Guide`, `a_Series_of_Words`.

<a name="terms-var-prop"></a> 
##### 変数/プロパティ (Variables / Properties)

ほとんどのコンテキストでは、 '変数' と 'プロパティ' という言葉は同じ意味です。 ただし、両方が同じコンテキストで一緒に使用されている場合は：

<a name="terms-property"></a> 
###### プロパティ (Properties)
通常、クラス内で定義された変数を指します。 たとえば、`BP_Barrel` ブループリントクラスに `bExploded` 変数がある場合、 `bExploded` は `BP_Barrel` クラスのプロパティと呼ばれます。

クラスのコンテキストでは、以前に定義されたデータへのアクセスを暗示するためによく使用されます。

<a name="terms-variable"></a> 
###### 変数 (Variables)
通常は、関数の引数または関数内のローカル変数として定義された変数を指します。 

クラスのコンテキストでは、その定義とそれが何を保持するかについての議論を、伝えるためによく使用されます。 

<a name="0"></a>
## 0. 原則

これらの原則は [idomatic.js style guide](https://github.com/rwaldron/idiomatic.js/) に即します。

<a name="0.1"></a>
### 0.1 あなたのUE4プロジェクトにすでにスタイルガイドがある場合は、それに従うべき

既存のスタイルガイドがあるチームまたはプロジェクトで作業している場合は、それを尊重する必要があります。 既存のスタイルガイドとこのガイドとの間に矛盾がある場合は、既存のスタイルガイドに従わなくてはなりません。

スタイルガイドは生き生きしたドキュメントでなければなりません。すべての用途に変更のメリットがあると感じる場合は、既存のスタイルガイドとこのガイドのスタイルガイドの変更を提案する必要があります。

> #### "スタイルを超えた議論は無意味です。スタイルガイドがあるべきで、あなたはそれに従うべきです"
> [_Rebecca Murphey_](https://rmurphey.com)

<a name="0.2"></a>
### 0.2 どんなに多くの人が貢献したとしても、どのUE4プロジェクトの、全ての構造、アセット、およびコードは、1人で作成したようにするべき

あるプロジェクトから別のプロジェクトに移っても、スタイルや構造を再学習してはいけません。 スタイルガイドに従うことで、不必要な推測や曖昧さがなくなります。

また、スタイルについて考える必要もなく、指示に従うだけで、より生産的な作成と保守が可能です。 このスタイルガイドはベストプラクティスを念頭に置いて書かれています。つまり、このスタイルガイドに従って、問題を追跡するのを最小限に抑えることができます。

<a name="0.3"></a>
### 0.3 チームのメンバの悪いスタイルを律するべき

スタイルガイドに反するまたはスタイルガイドが無いなどの、いずれかで作業している人がいる場合は指摘するようにしてください。

チーム内で働いたり、[Unreal Slackers](http://join.unrealslackers.org/) などのコミュニティで議論するときは、一貫性があるときに助けて助けを求めるのがはるかに簡単です。 誰も、誰かのブループリントスパゲッティを解くのを手伝ったり、理解できない名前のアセットを扱ったりするのを好む人はいません。

あなたの仕事の人が異なるが、一貫性があり、正真正銘のスタイルガイドに従うのを手助けしているなら、あなたはそれに適応できるはずです。 スタイルガイドに準拠していない場合は、ここで指示してください。

<a name="0.4"></a>
### 0.4 スタイルガイドの無いチームは、チームでは無い

UE4チームに参加するときは、最初の質問の1つが「あなたはスタイルガイドを持っていますか？」でなければなりません。 答えがノーなら、あなたはチームとして働く能力について懐疑的でなければなりません。

<a name="toc"></a>
<a name="table-of-contents"></a>
## 目次

> 1. [アセット命名規則](#anc)
> 1. [コンテンツディレクトリ構成](#structure)
> 1. [ブループリント](#bp)

<a name="anc"></a>
<a name="1"></a>
## 1. アセットの命名規則について ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

(( [アセットの命名規則 ](https://wiki.unrealengine.com/Assets_Naming_Convention_JP) ))

命名規則は、法律のように扱うべきです。 命名規則に準拠したプロジェクトでは、アセットの管理、検索、解析、維持管理が非常に簡単です。

ほとんどのものに接頭辞(Prefix)が付いています。接頭辞は一般的にアセットタイプの略語で、その後にアンダースコアが続きます。

<a name="base-asset-name"></a>
<a name="1.1"></a>
### 1.1 基本アセット名 - `Prefix_BaseAssetName_Variant_Suffix` ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

すべてのアセットに _基本アセット名_ _(Base Asset Name)_ が必要です。基本アセット名は、関連するアセットの論理的なグループを表します。この論理グループの一部であるアセットは、 `Prefix_BaseAssetName_Variant_Suffix`の標準に従うべきです。

パターン `Prefix_BaseAssetName_Variant_Suffix` を念頭に置いて常識的に使うことは、一般的には良いアセット名を保証するのに十分です。各要素に関するいくつかの詳細なルールがあります。

`Prefix`と` Suffix`は、以下の [Asset Name Modifier](#asset-name-modifiers) テーブルを介して、アセットタイプによって決定されます。

`BaseAssetName`は、このアセット群の文脈に関連した簡単で分かりやすい名前によって決定されるべきです。たとえば、Bobという名前のキャラクターがあった場合、Bobのすべてのアセットは `BaseAssetName` の ` Bob` という名前になります。

独特で特殊なアセットのバリエーションの場合、 `Variant` は、アセットの基本名のサブセットであるアセットの論理的なグループ分けを表す簡単で分かりやすい名前のいずれかです。例えば、Bobが複数のスキンを持っていた場合、これらのスキンは `BaseAssetName`として` Bob`を使用しますが、認識可能な `Variant`を含みます。 「Evil」スキンは `Bob_Evil` と呼ばれ、「Retro」スキンは `Bob_Retro` と呼ばれる。

ユニークではあるが一般的なアセットのバリエーションでは、 `Variant` は `01` から始まる2桁の数字です。例えば、岩石を作成する背景アーティストがいる場合、名前は `Rock_01`、` Rock_02`、 `Rock_03` などとなります。まれな例外を除いて、3桁の変種番号は必要ありません。アセットが100以上ある場合は、異なるベース名で複数のバリアント名を使用して整理することを検討する必要があります。

アセットバリアントの作成方法に応じて、バリアント名を連結することができます。たとえば、Arch Vizプロジェクトのフロアリングアセットを作成する場合は、`Flooring_Marble_01`, `Flooring_Maple_01`, `Flooring_Tile_Squares_01` などの連鎖変形を含むベース名 `Flooring` を使用する必要があります。

<a name="1.1-examples"></a>
#### 1.1 例

##### 1.1e1 Bob((キャラクター、人物、動物など))

| Asset Type              | Asset Name                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Skeletal Mesh           | SK_Bob                                                     |
| Material                | M_Bob                                                      |
| Texture (Diffuse/Albedo)| T_Bob_D                                                    |
| Texture (Normal)        | T_Bob_N                                                    |
| Texture (Evil Diffuse)  | T_Bob_Evil_D                                               |

##### 1.1e2 Rocks((静物、背景オブジェクトなど))

| Asset Type              | Asset Name                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Static Mesh (01)        | S_Rock_01                                                  |
| Static Mesh (02)        | S_Rock_02                                                  |
| Static Mesh (03)        | S_Rock_03                                                  |
| Material                | M_Rock                                                     |
| Material Instance (Snow)| MI_Rock_Snow                                               |

<a name="asset-name-modifiers"></a>
<a name="1.2"></a>
### 1.2 アセット名修飾子　![#](https://img.shields.io/badge/lint-supported-green.svg)

アセットの名前を付けるときは、これらのテーブルを使用してアセットの　[基本アセット名](#base-asset-name)　で使用する接頭辞(Prefix)と接尾辞(Suffix)を決定します。

#### セクション

> 1.2.1 [共通項目(Most Common)](#anc-common)

> 1.2.2 [アニメーション(Animations)](#anc-animations)

> 1.2.3 [人工知能(Artificial Intelligence)](#anc-ai)

> 1.2.4 [ブループリント(Blueprint)](#anc-bp)

> 1.2.5 [マテリアル(Materials)](#anc-materials)

> 1.2.6 [テクスチャ(Textures)](#anc-textures)

> 1.2.7 [その他(Miscellaneous)](#anc-misc)

> 1.2.8 [Paper 2D](#anc-paper2d)

> 1.2.9 [物理(Physics)](#anc-physics)

> 1.2.10 [サウンド(Sound)](#anc-sound)

> 1.2.11 [UI(User Interface)](#anc-ui)

> 1.2.12 [エフェクト(Effects)](#anc-effects)

<a name="anc-common"></a>
<a name="1.2.1"></a>
#### 1.2.1 Most Common ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Level / Map             |            |            | [ Mapsフォルダ配下に置くべき.](#2.4) |
| Level (Persistent)      |            | _P         |                                  |
| Level (Audio)           |            | _Audio     |                                  |
| Level (Lighting)        |            | _Lighting  |                                  |
| Level (Geometry)        |            | _Geo       |                                  |
| Level (Gameplay)        |            | _Gameplay  |                                  |
| Blueprint               | BP_        |            |                                  |
| Material                | M_         |            |                                  |
| Static Mesh             | S_ or SM_  |            | どちらか1つを選択。 S_ を優先        |
| Skeletal Mesh           | SK_        |            |                                  |
| Texture                 | T_         | _?         | [Textures](#anc-textures) を参照   |
| Particle System         | PS_        |            |                                  |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つを選択。 WBP_ を優先      |

<a name="anc-animations"></a>
<a name="1.2.2"></a>
#### 1.2.2 Animations ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Aim Offset              | AO_        |            |                                  |
| Aim Offset 1D           | AO_        |            |                                  |
| Animation Blueprint     | ABP_       |            |                                  |
| Animation Composite     | AC_        |            |                                  |
| Animation Montage       | AM_        |            |                                  |
| Animation Sequence      | A_ or AS_  |            | どちらか1つを選択。 A_ を優先        |
| Blend Space             | BS_        |            |                                  |
| Blend Space 1D          | BS_        |            |                                  |
| Level Sequence          | LS_        |            |                                  |
| Morph Target            | MT_        |            |                                  |
| Paper Flipbook          | PFB_       |            |                                  |
| Rig                     | Rig_       |            |                                  |
| Skeletal Mesh           | SK_        |            |                                  |
| Skeleton                | SKEL_      |            |                                  |

<a name="anc-ai"></a>
<a name="1.2.3"></a>
### 1.2.3 Artificial Intelligence ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| AI Controller           | AIC_       |            |                                  |
| Behavior Tree           | BT_        |            |                                  |
| Blackboard              | BB_        |            |                                  |
| Decorator               | BTDecorator_ |          |                                  |
| Service                 | BTService_ |            |                                  |
| Task                    | BTTask_    |            |                                  |

<a name="anc-bp"></a>
<a name="1.2.4"></a>
### 1.2.4 Blueprint ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Blueprint               | BP_        |            |                                  |
| Blueprint Function Library | BPFL_   |            |                                  |
| Blueprint Interface     | BPI_       |            |                                  |
| Blueprint Macro Library | BPML_      |            | 可能な限り、マクロライブラリは使わない。 |
| Enumeration             | E          |            | アンダースコアを付けない。                   |
| Structure               | F or S     |            | アンダースコアを付けない。                   |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つを選択。 WBP_ を優先      |

<a name="anc-materials"></a>
<a name="1.2.5"></a>
### 1.2.5 Materials ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Material                | M_         |            |                                  |
| Material (Post Process) | PP_        |            |                                  |
| Material Function       | MF_        |            |                                  |
| Material Instance       | MI_        |            |                                  |
| Material Parameter Collection | MPC_ |            |                                  |
| Subsurface Profile      | SP_ or SSP_|            | どちらか1つを選択。 SP_ を優先       |
| Physical Materials      | PM_        |            |                                  |

<a name="anc-textures"></a>
<a name="1.2.6"></a>
### 1.2.6 Textures ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Texture                 | T_         |            |                                  |
| Texture (Diffuse/Albedo/Base Color)| T_ | _D      |                                  |
| Texture (Normal)        | T_         | _N         |                                  |
| Texture (Roughness)     | T_         | _R         |                                  |
| Texture (Alpha/Opacity) | T_         | _A         |                                  |
| Texture (Ambient Occlusion) | T_     | _O or _AO  | どちらか1つを選択。 _O を優先       |
| Texture (Bump)          | T_         | _B         |                                  |
| Texture (Emissive)      | T_         | _E         |                                  |
| Texture (Mask)          | T_         | _M         |                                  |
| Texture (Specular)      | T_         | _S         |                                  |
| Texture (Packed)        | T_         | _*         | 下記の注記 [packing](#anc-textures-packing) を参照 |
| Texture Cube            | TC_        |            |                                  |
| Media Texture           | MT_        |            |                                  |
| Render Target           | RT_ or RTT_|            | どちらか1つを選択。 RT_ を優先       |
| Cube Render Target      | RTC_       |            |                                  |
| Texture Light Profile   | TLP        |            |                                  |

<a name="anc-textures-packing"</a>
<a name="1.2.6.1"></a>
#### 1.2.6.1 Texture Packing ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

テクスチャデータの複数のレイヤを1つのテクスチャにパックするのが一般的な方法です。 これの一例は、発光（エミッシブ）、粗さ（ラフネス）、環境遮蔽（アンビエントオクルージョン）をテクスチャの赤、緑、青のチャンネルとしてまとめたものです。 接尾辞を決定するには、上の指定された接尾辞の文字を単純に重ねます。 `_ERO`。

> Diffuse/AlbedoのアルファチャンネルにAlpha/Opacityレイヤーを含めることは一般的に受け入れられます。これは一般的な方法で、 `_D` 接尾辞に ` A` を追加することはオプションです。

Diffuse/AlbedoのアルファチャンネルのAlpha/Opacityマスク以外の4チャンネルのデータをテクスチャ（RGBA）にパッキングするのはお勧めできません。

<a name="anc-misc"></a>
<a name="1.2.7"></a>
### 1.2.7 Miscellaneous ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Animated Vector Field   | VFA_       |            |                                  |
| Camera Anim             | CA_        |            |                                  |
| Color Curve             | Curve_     | _Color     |                                  |
| Curve Table             | Curve_     | _Table     |                                  |
| Data Asset              | *_         |            | 接頭辞はクラスに基づいている必要があります |
| Data Table              | DT_        |            |                                  |
| Float Curve             | Curve_     | _Float     |                                  |
| Foliage Type            | FT_        |            |                                  |
| Force Feedback Effect   | FFE_       |            |                                  |
| Landscape Grass Type    | LG_        |            |                                  |
| Landscape Layer         | LL_        |            |                                  |
| Matinee Data            | Matinee_   |            |                                  |
| Media Player            | MP_        |            |                                  |
| Object Library          | OL_        |            |                                  |
| Redirector              |            |            | これらはできるだけ早く修正する必要があります |
| Sprite Sheet            | SS_        |            |                                  |
| Static Vector Field     | VF_        |            |                                  |
| Touch Interface Setup   | TI_        |            |                                  |
| Vector Curve            | Curve_     | _Vector    |                                  |

<a name="anc-paper2d"></a>
<a name="1.2.8"></a>
### 1.2.8 Paper 2D ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Paper Flipbook          | PFB_       |            |                                  |
| Sprite                  | SPR_       |            |                                  |
| Sprite Atlas Group      | SPRG_      |            |                                  |
| Tile Map                | TM_        |            |                                  |
| Tile Set                | TS_        |            |                                  |

<a name="anc-physics"></a>
<a name="1.2.9"></a>
### 1.2.9 Physics ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Physical Material       | PM_        |            |                                  |
| Physical Asset	  | PHYS_      |            |                                  |
| Destructible Mesh       | DM_        |            |                                  |

<a name="anc-sounds"></a>
<a name="1.2.10"></a>
### 1.2.10 Sounds ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Dialogue Voice          | DV_        |            |                                  |
| Dialogue Wave           | DW_        |            |                                  |
| Media Sound Wave        | MSW_       |            |                                  |
| Reverb Effect           | Reverb_    |            |                                  |
| Sound Attenuation       | ATT_       |            |                                  |
| Sound Class             |            |            | 接頭辞/接尾辞を付けません。 SoundClassesフォルダ配下に置べき |
| Sound Concurrency       |            | _SC        | SoundClassの後に名前付けるべき |
| Sound Cue               | A_         | _Cue       |                                  |
| Sound Mix               | Mix_       |            |                                  |
| Sound Wave              | A_         |            |                                  |

<a name="anc-ui"></a>
<a name="1.2.11"></a>
### 1.2.11 User Interface ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Font                    | Font_      |            |                                  |
| Slate Brush             | Brush_     |            |                                  |
| Slate Widget Style      | Style_     |            |                                  |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つを選択。 WBP_ を優先      |

<a name="anc-effects"></a>
<a name="1.2.12"></a>
### 1.2.12 Effects ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | 注意(Notes)                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Particle System         | PS_        |            |                                  |
| Material (Post Process) | PP_        |            |                                  |

<a name="2"></a>
<a name="structure"></a>
## 2. コンテンツディレクトリの構成について ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

アセット名と同様に重要なことに、プロジェクトのディレクトリ構造のスタイルも法律のように扱うべきです。 アセットの命名規則とコンテンツディレクトリ構造が両立し、いずれかの違反は不要な混乱の原因となります。

UE4プロジェクトのコンテンツをレイアウトする方法は複数あります。 このスタイルでは、アセットをグループ化する別の共通構造ではなく、特定のタイプのアセットを検索するために、コンテンツブラウザのフィルタリングと検索機能にもっと依存する構造を使用します。

> 上記の [命名規則](#1.2) を使用している場合、フォルダに `Meshes`, `Textures`, および `Materials`などの類似の型のアセットを格納することは、アセットの型がすでにソートされているため、 プレフィックスだけでなく、コンテンツブラウザでフィルタリングすることができます。


<a name="2e1"><a>
### 2e1 プロジェクトのコンテンツ構造の例
<pre>
|-- Content
    |-- <a href="#2.2">GenericShooter</a>
        |-- Art
        |   |-- Industrial
        |   |   |-- Ambient
        |   |   |-- Machinery
        |   |   |-- Pipes
        |   |-- Nature
        |   |   |-- Ambient
        |   |   |-- Foliage
        |   |   |-- Rocks
        |   |   |-- Trees
        |   |-- Office
        |-- Characters
        |   |-- Bob
        |   |-- Common
        |   |   |-- <a href="#2.7">Animations</a>
        |   |   |-- Audio
        |   |-- Jack
        |   |-- Steve
        |   |-- <a href="#2.1.3">Zoe</a>
        |-- <a href="#2.5">Core</a>
        |   |-- Characters
        |   |-- Engine
        |   |-- <a href="#2.1.2">GameModes</a>
        |   |-- Interactables
        |   |-- Pickups
        |   |-- Weapons
        |-- Effects
        |   |-- Electrical
        |   |-- Fire
        |   |-- Weather
        |-- <a href="#2.4">Maps</a>
        |   |-- Campaign1
        |   |-- Campaign2
        |-- <a href="#2.8">MaterialLibrary</a>
        |   |-- Debug
        |   |-- Metal
        |   |-- Paint
        |   |-- Utility
        |   |-- Weathering
        |-- Placeables
        |   |-- Pickups
        |-- Weapons
            |-- Common
            |-- Pistols
            |   |-- DesertEagle
            |   |-- RocketPistol
            |-- Rifles
</pre>

この構造の理由は、以下のサブセクションに記載されています。

### セクション

> 2.1 [フォルダ名](#structure-folder-names)

> 2.2 [トップレベルのフォルダ](#structure-top-level)

> 2.3 [Developers フォルダ](#structure-developers)

> 2.4 [Maps フォルダ](#structure-maps)

> 2.5 [Core フォルダ](#structure-core)

> 2.6 [`Assets` and `AssetTypes`](#structure-assettypes)

> 2.7 [Large Sets](#structure-large-sets)

> 2.8 [Material Library](#structure-material-library)


<a name="2.1"></a>
<a name="structure-folder-names"><a>
### 2.1  フォルダ名 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

以下はコンテンツディレクトリ構造での、任意のフォルダへの共通な名前付けルールです。

<a name="2.1.1"></a>
#### 2.1.1 常に PascalCase を使うこと [<sup>*</sup>](#terms-cases) ![#](https://img.shields.io/badge/lint-supported-green.svg)

PascalCaseは、大文字で名前を始めることを意味し、スペースを使用する代わりに、すべての次の単語も大文字で始まります。 たとえば、`DesertEagle`, `RocketPistol`,および `ASeriesOfWords` などです。

[記法](#terms-cases)を参照。

<a name="2.1.2"></a>
#### 2.1.2 絶対にスペースを使わないこと ![#](https://img.shields.io/badge/lint-supported-green.svg)

[常に PascalCase を使うこと](#2.1.1) を再徹底したうえで、絶対にスペースを使わないでください。 スペースによって、さまざまな開発ツールやバッチ処理などで失敗する可能性があります。 理想的には、プロジェクトのルートには空白が含まれておらず、 `C:\Users\My Name\My Documents\Unreal Projects` の代わりに `D:\Project`のような場所に置かれているのが理想的です。

<a name="2.1.3"></a>
#### 2.1.3 絶対にUnicodeと、その他の記号を使わないこと ![#](https://img.shields.io/badge/lint-supported-green.svg)

あなたのゲームキャラクターの名前が「Zoë」の場合、そのフォルダ名は `Zoe`でなければなりません。 Unicodeは、解析ツールやUE4の一部ではパス(path)に含まれるのUnicode文字もサポートされないため [スペース](#2.1.2) より悪くなることがあります。

これに関連して、プロジェクトに [不可解な問題](https://answers.unrealengine.com/questions/101207/undefined.html) があり、コンピュータのユーザー名がUnicode文字（つまり、あなたの名前は `Zoë`）である場合や、 `My Documents`フォルダ以下にUE4プロジェクトを置いている場合は、この問題を抱えています。 ただ単にUE4プロジェクトを `D:\Project` などに移動するだけで、これらの摩訶不思議な問題が解決するでしょう。

`@`, `-`, `_`, `,`, `*`, と `#` のような `a-z`, `A-Z`, 及び `0-9` 以外の文字を使うことによる、 他のプラットフォーム、ソース管理、および脆弱な解析ツールの問題を追跡することは困難です。

<a name="2.2"></a>
<a name="structure-top-level"><a>
### 2.2 プロジェクト固有アセットには、トップレベルのフォルダを使うこと ![#](https://img.shields.io/badge/lint-supported-green.svg)

全てのプロジェクトに関するアセットは、プロジェクトと同名フォルダ以下に存在するべきです。 たとえば、プロジェクト名が「Generic Shooter」の場合、そのコンテンツの _全て_ は `Content/GenericShooter` 以下に存在する必要があります。

> `Developers` フォルダは、プロジェクトが依存しているアセット用ではないため、プロジェクト固有のものではありません。 これに関する詳細は [Developers フォルダ](#2.3)  を参照してください。

このアプローチには複数の理由があります。

<a name="2.2.1"></a>
#### 2.2.1 グローバルなアセットは作成しないこと

<!-- todo review -->
多くの場合、コードスタイルガイドでは、グローバル名前空間を汚染しない事と書かれています。このガイドも同じ原則に従います。 アセットがプロジェクトフォルダの外に存在することが許される場合、フォルダ内にないアセットがアセットを整理する必要がないという悪い行為を促すため、厳密な構造レイアウトを強制するのはずっと困難になります。

すべてのアセットは目的を持っている必要があります。そうでなければ、プロジェクトに属していません。 アセットが実験的なテストであり、プロジェクトで使用すべきでない場合は、 [`Developers`](#2.3) フォルダに置く必要があります。 

<a name="2.2.2"></a>
#### 2.2.2 移行時の衝突の削減

複数のプロジェクトに取り組んでいるときに、チームが両方のプロジェクトに役立つものを作っていれば、あるプロジェクトからもう片方のプロジェクトへ、アセットをコピーするのが一般的です。このような事が起きたときに、コピーを実行する最も簡単な方法は、コンテンツブラウザの移行機能を使用することです。それは選択したアセットだけでなく、その全ての依存関係を持つアセットをコピーするでしょう。

これらの依存関係は、簡単に問題を引き起こす可能性があります。 2つのプロジェクトのアセットにトップレベルのフォルダがなく、同様の名前が付けられているか、すでに以前に移行されたアセットがある場合は、新しい移行によって誤って既存のアセットの変更が消去される可能性があります。

これはまた、EpicのMarketplaceスタッフが提出されたアセットに対して同じポリシーを強制する主な理由です。

移行後の、コンテンツブラウザの '参照の置き換え(Replace References)' ツールを使用すると、明らかにマージが保留されてた、プロジェクトのトップレベルのフォルダに属していない事が明確なアセットの追加されたて、アセットの安全なマージが可能です。ひとたびアセットがマージされ、完全に移行されると、コンテンツツリーに別のトップレベルのフォルダは存在しないはずです。この方法は、完全に安全な移行を行うために _100％_ 保証されています。

<a name="2.2.2e1"></a>
##### 2.2.2e1 マスターマテリアルの例

たとえば、あるプロジェクトに別のプロジェクトで使用したいマスターマテリアルを作成し、そのアセットを移行したとします。このアセットがトップレベルのフォルダにない場合、 `Content/MaterialLibrary/M_Master` のような名前を持つ可能性があります。ターゲットプロジェクトにすでにマスタマテリアルがない場合、これは問題なく動作するはずです。

一方または両方のプロジェクトの作業が進行するにつれて、それぞれのマスターマテリアルは、通常の開発過程のために、特定のプロジェクトに合わせて変更される可能性があります。

たとえば、あるプロジェクトのアーティストが静的メッシュ用の汎用的なモジュラーセットを作成し、誰かがその静的メッシュのセットを2番目のプロジェクトに含める場合など、問題が発生します。アセットを作成したアーティストが、指示されているとおりに `Content/MaterialLibrary/M_Master` に基づいてマテリアルインスタンスを使用した場合、移行が実行されると、以前に移行された `Content/MaterialLibrary/M_Master` のアセットと競合する可能性が高くなります。

この問題は、予測するのが難しく、説明するのが難しい場合があります。静的メッシュを移動する人は、プロジェクトのマスターマテリアルの開発に精通している人と同じ人ではないかもしれませんし、問題の静的メッシュがマスターマテリアルに依存しているマテリアルインスタンスに依存していることに気づいていないかもしれません。しかし、移行ツールでは、依存関係のチェーン全体が機能する必要があるため、これらのアセットを他のプロジェクトにコピーするときに `Content/MaterialLibrary/M_Master`を強制的に取得し、既存のアセットを上書きします。

この時点で、両方のプロジェクトのマスタマテリアルが互換性がない場合は、アセットがトップレベルのフォルダに格納されていないため、プロジェクトのマテリアルライブラリ全体や、すでに移行されている可能性のあるその他の依存関係を壊す可能性があります。静的メッシュの単純な移行は、現在非常に醜い作業になります。

<a name="2.2.3"></a>
#### 2.2.3 サンプル、テンプレート、マーケットプレイスのコンテンツはノーリスクです

[移行時の衝突の削減](#2.2.2) の拡張版では、チームメンバーがサンプルコンテンツ、テンプレートファイル、またはマーケットプレイスから購入したアセットを追加することを決定した場合、プロジェクトのトップレベルフォルダに一意の名前が付けられていない限り、これらの新しいアセットがプロジェクトに干渉しないことが保証されます。

マーケットプレイスのコンテンツを [トップレベルのフォルダルール](#2.2) に完全に準拠させることはできません。 トップレベルのフォルダに大部分のコンテンツを持つ多くのアセットが存在しますが、Epicのサンプルコンテンツやグローバルな `Content` フォルダを汚染するレベルファイルも変更されている可能性があります。

[トップレベルのフォルダ](#2.2) を遵守する場合、マーケットプレイスの競合は、2つのマーケットプレイスアセットのEpicサンプルコンテンツが同じである場合に起こります。 すべてのアセットがプロジェクト固有のフォルダに含まれている場合、フォルダに移動した可能性があるサンプルコンテンツが含まれていれば、プロジェクトは中断しません。

#### 2.2.4 DLC((ダウンロードコンテンツ))、サブプロジェクト、およびパッチは簡単に維持できます

DLCをリリースする予定のプロジェクト、または複数のサブプロジェクトが関連付けられている場合、これらのプロジェクトは移行されるか、単にビルドされないことがあります。これらのプロジェクトに関連するアセットには、独自のトップレベルコンテンツフォルダが必要です。 これにより、DLCはメインプロジェクトのコンテンツとは別に料理がはるかに簡単になります。 サブプロジェクトは、最小限の労力で入退出することもできます。 アセットのマテリアルを変更したり、パッチで非常に特殊なアセットオーバーライド動作を追加する必要がある場合は、これらの変更をパッチフォルダに簡単に入れて、コアプロジェクトを壊すことなく安全に作業できます。

<a name="2.3"></a>
<a name="structure-developers"></a>
### 2.3 ローカルテスト用にDevelopersフォルダを使うこと ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

プロジェクトの開発中に、チームメンバーがコアプロジェクトを危険にさらすことなく自由に実験できる「サンドボックス」を持つことは非常に一般的です。この作業が進行中である可能性があるため、これらのチームメンバはプロジェクトのソース管理サーバーにアセットを配置することができます。すべてのチームがデベロッパーフォルダの使用を必要とするわけではありませんが、それらを使用するチームはソース管理に提出されたアセットに共通の問題に遭遇することがよくあります。

チームメンバーが、使用準備が整っていないアセットを誤って使用することは非常に簡単で、そのアセットが削除されると問題が発生する可能性があります。たとえば、アーティストが静的メッシュのモジュラセットを反復処理していて、サイジングとグリッドのスナッピングが正しく行われているとします。世界の建築家がこれらのアセットをメインプロジェクトフォルダに見た場合、彼らは信じられないほどの変更や削除を受ける可能性があることを知らずに、レベル全体でそれらのアセットを使用するかもしれません。これにより、チームの全員が大量の再作業を行うことになります。

これらのモジュラーアセットがDevelopersフォルダに配置されている場合、世界の建築家は決してそれらを使用する理由があってはならず、問題は起こりません。コンテンツブラウザには、デベロッパーフォルダを非表示にする特定の表示オプションがあります（デフォルトでは非表示になっています）ので、通常の使用状態で誤ってデベロッパーアセットを使用することはできません。

アセットを使用できるようになると、アーティストはアセットをプロジェクト固有のフォルダに移動し、リダイレクタを修正するだけです。これは本質的にアセットを実験から生産に「促進」しています。

<a name="2.4"></a>
<a name="structure-maps"></a>
### 2.4 すべてのMap[<sup>*</sup>](#terms-level-map) ファイルは、Mapsフォルダに配置すること ![#](https://img.shields.io/badge/lint-supported-green.svg)

Mapファイルは信じられないほど特殊で、特にサブレベルやストリーミングレベルで作業する場合は、すべてのプロジェクトで独自のマップ命名システムを使用するのが一般的です。特定のプロジェクトでどのようなマップ体系が整っていても、すべてのレベルは `/Content/Project/Maps` 以下に属している必要があります。

場所を説明することなく特定の地図を開くように誰かに指示できることは、時間の節約と一般的な「クオリティ・オブ・ライフ」改善です。 `Maps/Campaign1/`や `Maps/Arenas`のように、レベルが`Maps`のサブフォルダ内にあるのが一般的ですが、ここで最も重要なのは  `/Content/Project/Maps`。

これにより、エンジニア向けの調理作業も簡単になります。ビルドプロセスのレベルを狂わせることは、それらのために任意のフォルダを掘り下げなければならない場合、非常に不快になります。チームの地図がすべて1か所にある場合、誤ってビルド内の地図を調理するのはずっと難しくなります。また、QAプロセスだけでなくビルドスクリプトも簡単に作成できます。

<a name="2.5"></a>
<a name="structure-core"></a>
### 2.5 重要なブループリントやその他のアセットのためは、 `Core` フォルダを使うこと ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

プロジェクトの動作に不可欠なアセットに `/Content/Project/Core`フォルダを使用してください。たとえば、 `GameMode`、` Character`、 `PlayerController`、` GameState`、 `PlayerState`、および関連するブループリントはここに属していなければなりません。

これにより、他のチームメンバーにとって非常に明確な「これらに触れないでください」というメッセージになります。非エンジニアは `Core`フォルダに入る理由はほとんどありません。優れたコード構造スタイルに従えば、デザイナーは、機能を公開する子クラスでゲームプレイを調整する必要があります。世界の建築家は、潜在的に悪用されるベースクラスではなく、指定されたフォルダでプレハブブループリントを使用する必要があります。

たとえば、プロジェクトがレベルに配置できるピックアップを必要とする場合、ピックアップの基本動作を定義する基本ピックアップクラスが `Core/Pickups` に存在するはずです。 Health または Ammoなどの特定のピックアップは、`/Content/Project/Placeables/Pickups/`のようなフォルダに存在するはずです。ゲームデザイナーはこのフォルダ内のピックアップを定義し調整することができますが、プロジェクト全体のピックアップを意図せず破損する可能性があるため、`Core/Pickups` に触れてはいけません。

<a name="2.6"></a>
<a name="structure-assettypes"></a>
### 2.6 `Assets`または` AssetTypes`というフォルダを作成しないこと ![#](https://img.shields.io/badge/lint-supported-green.svg)

<a name="2.6.1"></a>
#### 2.6.1 `Assets`という名前のフォルダを作成することは冗長です ![#](https://img.shields.io/badge/lint-supported-green.svg)

全てのアセットはアセットです。   

<a name="2.6.2"></a>
#### 2.6.2 `Meshes`、` Textures`、または `Materials`という名前のフォルダを作成することは冗長です ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのアセット名は、そのアセットタイプを念頭に置いて命名されます。これらのフォルダは冗長な情報のみを提供し、これらのフォルダの使用は、コンテンツブラウザが提供する堅牢で使いやすいフィルタリングシステムで簡単に置き換えることができます。

 `Environment/Rocks/` に静的メッシュだけを表示したいですか？静的メッシュフィルターをオンにするだけです。すべてのアセットの名前が正しく指定されている場合は、接頭辞に関係なくアルファベット順にソートされます。静的メッシュとスケルトンメッシュの両方を表示したいですか？両方のフィルターをオンにするだけです。これにより、コンテンツブラウザのツリービューで2つのフォルダを `Control-Click` する必要がなくなります。

> これはまた、アセットの完全なパス名をほとんど利益のために拡張します。静的メッシュの `S_` 接頭辞は2文字だけですが、` Meshes/`は7文字です。

これをしないと、誰かが静的メッシュやテクスチャを `Materials`フォルダに置くことを避けることができなくなります。

<a name="2.7"></a>
<a name="structure-large-sets"></a>
### 2.7 非常に大きなアセットのセットは、それら独自のフォルダレイアウトを取ります ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

これは、 [2.6](#2.6) の擬似例外として見ることができます。

各アセットに独自の目的がある膨大な量の関連ファイルを持つ特定のアセットタイプがあります。 最も一般的な2つは、アニメーションとオーディオのアセットです。 一緒に属しているこれらのアセットが15以上あることが判明した場合、それらは一緒になっている必要があります。

たとえば、複数の文字にまたがって共有されるアニメーションは、`Characters/Common/Animations` にあり、`Locomotion` や `Cinematic` などのサブフォルダを持つことがあります。

> テクスチャやマテリアルなどのアセットには適用されません。 大量の岩石がある場合、 `Rocks` フォルダは大量のテクスチャを持つのが一般的ですが、これらのテクスチャは一般的には特定の岩石にしか関連しておらず、適切に名前を付ける必要があります。 これらのテクスチャが [Material Library](#2.8) の一部であっても

<a name="2.8"></a>
<a name="structure-material-library"></a>
### 2.8 `MaterialLibrary` ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

プロジェクトでマスターマテリアル、レイヤードマテリアル、またはアセットのサブセットに属しない再利用可能なマテリアルやテクスチャを使用する場合、これらのアセットは `Content/Project/MaterialLibrary` に配置する必要があります。

このようにして、すべての「グローバル」マテリアルは生きる場所を持ち、簡単に見つけられます。

> これにより、プロジェクト内で「材料インスタンスのみ使用」ポリシーを実行することも非常に簡単になります。すべてのアーティストとアセットがマテリアルインスタンスを使用する必要がある場合は、存在するはずの正規のアセットのみがこのフォルダ内にあります。 `MaterialLibrary` 以外のフォルダ内のベースマテリアルを検索することで、これを簡単に確認できます。

`MaterialLibrary` は、純粋にマテリアルである必要はありません。共有ユーティリティテクスチャ、マテリアル関数、およびこのようなその他のものは、意図した目的を指定するフォルダ内にここに格納する必要があります。例えば、一般的なノイズテクスチャは `MaterialLibrary/Utility` に置かなければなりません。

テストやデバッグのためのマテリアルは `MaterialLibrary/Debug` の中になければなりません。これにより、出荷前にデバッグマテリアルをプロジェクトから簡単に取り除くことができ、参照エラーが表示されている場合に生産アセットがそれらを使用している場合、信じられないほど明らかになります。

<a name="3"></a>
<a name="bp"></a>
## 3. ブループリントについて ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

このセクションでは、Blueprintクラスとその内部について説明します。 可能であれば、スタイルルールは [Epic's Coding Standard](https://docs.unrealengine.com/latest/INT/Programming/Development/CodingStandard) に準拠しています。

思い出してください：Blueprintのノーディングは、酷くドジっても大丈夫です。 （[KorkuVeren](http://github.com/KorkuVeren)曰く）

### セクション

> 3.1 [コンパイル(Compiling)](#bp-compiling)

> 3.2 [変数(Variables)](#bp-vars)

> 3.3 [関数(Functions)](#bp-functions) 

> 3.4 [グラフエディタ(Graphs)](#bp-graphs) 

<a name="3.1"></a>
<a name="bp-compiling"></a>
### 3.1 コンパイル(Compiling) ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのブループリントは、警告及びエラー無しで、コンパイルする必要があります。 放置しておくと非常に恐ろしい予期しない動作へと次々に連なるので、ブループリントの警告とエラーを直ちに修正するべきです。

破損したブループリントをSVN/git等に(ソースのバージョン管理システム)にコミット **しないでください**。 それらをどうしてもSVN等に保存する必要がある場合は、代わりにそれらを葬ってください。

壊れたブループリントは、壊れた参照、予期しない動作、料理の失敗、頻繁で不要な再コンパイルなど、別の方法で現れる問題を引き起こす可能性があります。 壊れたブループリントはあなたのゲーム全体を破壊する力を持っています。

<a name="3.2"></a>
<a name="bp-vars"></a>
### 3.2 変数(Variables) ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

(( [ブループリントの変数](https://docs.unrealengine.com/latest/JPN/Engine/Blueprints/UserGuide/Variables/index.html)を参照 ))

「変数」と「プロパティ」という言葉は、同じ意味で使用できます。

#### セクション

> 3.2.1 [名前付け(Naming)](#bp-vars)

> 3.2.2 [編集可能(Editable)](#bp-vars-editable)

> 3.2.3 [分類(Categories)](#bp-vars-categories)

> 3.2.4 [アクセス(Access)](#bp-vars-access)

> 3.2.5 [高度(Advanced)](#bp-vars-advanced)

> 3.2.6 [一時的(Transient)](#bp-vars-transient)

> 3.2.7 [保存(SaveGame)](#bp-vars-savegame)

> 3.2.8 [設定(Config)](#bp-vars-config)

<a name="3.2.1"></a>
<a name="bp-var-naming"></a>
#### 3.2.1 名前付け ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

<a name="3.2.1.1"></a>
<a name="bp-var-naming-nouns"></a>
##### 3.2.1.1 名詞 ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

すべての非ブール変数名は、明確で明確で説明的な名詞でなければなりません。

<a name="3.2.1.2"></a>
<a name="bp-var-naming-case"></a>
##### 3.2.1.2 PascalCase ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべての非ブール変数は [PascalCase](#terms-cases) の形式でなければなりません。

<a name="3.2.1.2e"></a>
###### 3.2.1.2e 例:

* `Score`
* `Kills`
* `TargetPlayer`
* `Range`
* `CrosshairColor`
* `AbilityID`

<a name="3.2.1.3"></a>
<a name="bp-var-bool-prefix"></a>
##### 3.2.1.3 Boopleanの接頭辞は `b`　にするべき ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのブール値はPascalCaseで命名するべきですが、先頭に小文字の `b` を付けます。

例： `Dead`と` Evil` **ではなく**、 `bDead`と` bEvil`を使用して下さい。

UE4 Blueprint editors は、変数の使いやすい表示に `b` を含めないことを知っています。

<a name="3.2.1.4"></a>
<a name="bp-var-bool-names"></a>
##### 3.2.1.4 ブール値の命名規則 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

<a name="3.2.1.4.1"></a>
###### 3.2.1.4.1 一般かつ独立した状態の情報(General And Independent State Information) ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのブール値は、一般的な情報を表すならば可能なときには叙述的な形容詞として命名されるべきである。 その変数を疑問として含む単語、例えば `Is`を含めないでください。 これは関数用に予約されています。

例： `bIsDead` と `bIsHostile` **ではなく**、 `bDead`と` bHostile` を使用して下さい。

`bRunning`のような動詞を使わないようにしてください。 動詞は複雑な状態につながる傾向があります。

<a name="3.2.1.4.2"></a>
###### 3.2.1.4.2 複合した状態(Complex States) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

複合および/または従属状態を表すためにブール値を使用しないでください。 これにより、状態の追加と削除が複雑になり、もはや簡単には読み込めなくなります。 代わりに列挙を使用してください。

例：武器を定義するときに、武器を再装備したり装備することが**できない場合は**、 bReloadingを使用せず、bEquippingを使用しないでください。 `EWeaponState`という名前の列挙体を定義し、代わりに` WeaponState`という名前のこの型の変数を使用してください。 これにより、武器に新しい状態を追加することがはるかに容易になります。

例： `bWalking`や` bSprinting`が必要な場合は `bRunning`を**使わないでください**。 これは、明確に定義された状態名を持つ列挙として定義する必要があります。

<a name="3.2.1.5"></a>
<a name="bp-vars-naming-context"></a>
##### 3.2.1.5 コンテキストの考慮(Considered Context) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Blueprintのすべての変数への参照は常にそのコンテキストを持つので、すべての変数名はコンテキストと重複してはいけません。

<a name="3.2.1.5e"></a>
###### 3.2.1.5e 例:

`BP_PlayerCharacter`というBlueprintを考えてみましょう。

**悪い場合**

* `PlayerScore`
* `PlayerKills`
* `MyTargetPlayer`
* `MyCharacterName`
* `CharacterSkills`
* `ChosenCharacterSkin`

これらの変数はすべて重複して名前が付けられています。 これらの変数を定義しているのは `BP_PlayerCharacter`なので、変数はその変数が属する`BP_PlayerCharacter`を表しています。

**良い場合**

* `Score`
* `Kills`
* `TargetPlayer`
* `Name`
* `Skills`
* `Skin`

((上記のように、`BP_PlayerCharacter`に属する変数であることを考慮して、シンプルに表すべきです))

<a name="3.2.1.6"></a>
<a name="bp-vars-naming-atomic"></a>
##### 3.2.1.6 アトミック型名を変数名に含める _べきでない_ (Do _Not_ Include Atomic Type Names) ![#](https://img.shields.io/badge/lint-supported-green.svg)

Atomicまたはプリミティブ変数は、ブール値、整数、浮動小数点数、および列挙型など、最も単純な形式のデータを表す変数です。

ブループリントで作業する場合、StringやVectorはスタイルの観点からアトミック的であるとみなされますが、正確にはアトミックではありません。

> Vectorは3つの浮動小数点で構成されますが、Vectorは回転子と同じように全体として操作することができます。

> Text変数をアトミックなものと見なすのではなく、密かにローカライゼーション機能を隠していますか？文字列のアトミックタイプは `Text`ではなく` String`です。

Atomic変数の型名はその名前に含まれるべきではありません。

例： ` ScoreFloat`、 `FloatKills`、` DescriptionString` **ではなく** `Score`、` Kills`、 `Description` を使用します。

このルールの唯一の例外は、変数が変数の型を持たない名前を使うのが読みにくい場合に、変数が '数えられる何か' を表していることです。

例：フェンスジェネレータは、X個のポストを生成する必要があります。 `Posts`の` Posts`ではなく `NumPosts`や` PostsCount`にXをストアすると、 `Post`という名前の変数型の配列として読み込まれる可能性があります。

<a name="3.2.1.7"></a>
<a name="bp-vars-naming-complex"></a>
##### 3.2.1.7 非アトミック型名は変数名に含めるべき (Do Include Non-Atomic Type Names) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

非Atomicまたは複合変数は、データをアトミック変数の集合として表す変数です。 `Text`や` Name`のような隠れた振る舞いを持つ構造体、クラス、インタフェース、プリミティブはすべてこのルールの対象となります。

> アトミック変数型の配列は変数のリストですが、配列は変数型の '原子性(atomicness)' を変更しません。

これらの変数は、コンテキストを考慮しながら型名を含める必要があります。

クラスが複雑な変数のインスタンスを所有している場合、つまり `BP_PlayerCharacter`が` BP_Hat`を所有している場合は、名前を変更することなく変数型として格納する必要があります。

例： `` MyHat``、 `MyFlag`、` PlayerAbility` **ではなく** `Hat`、` Flag`、 `Ability` を使用します。

複雑な変数が表す値をクラスが所有していない場合は、変数型とともに名詞を使用する必要があります。

例： `BP_Turret`が` BP_PlayerCharacter`を対象とする能力を持っているならば、 `BP_Turret`の文脈で` TargetPlayer`としてその目標を保存する必要があります。それは所有していません。


<a name="3.2.1.8"></a>
<a name="bp-vars-naming-arrays"></a>
##### 3.2.1.8 ((Type:))配列(Arrays) ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

配列は上記と同じ命名規則に従いますが、複数の名詞として命名する必要があります。

例： `TargetList`、` HatArray`、 `EnemyPlayerArray` **ではなく** `Target`、` Hats`、 `EnemyPlayers` を使用します。

<a name="3.2.2"></a>
<a name="bp-vars-editable"></a>
#### 3.2.2 ((option:))Editable Variables((パブリックで編集可能のon/off)) ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

ブループリントの動作を設定するために値を変更するのに安全なすべての変数は、`編集可能` としてマークする必要があります。

逆に、変更が安全でない、または設計者に公開されるべきでないすべての変数は、エンジニアリング上の理由で、変数が `Expose On Spawn` としてマークされていない限り、編集可能とマークされてはなりません。

変数を `編集可能` として任意にマークしないでください。

<a name="3.2.2.1"></a>
<a name="bp-vars-editable-tooltips"></a>
##### 3.2.2.1 ((option:))Tooltips((変数の追加情報として表示する内容)) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

編集可能とマークされた変数を含むすべての `Editable`変数は、` Expose On Spawn`としてマークすることができるので、この値の変更がブループリントの動作にどのように影響するかを説明する `Tooltip`フィールドに記述する必要があります。

<a name="3.2.2.2"></a>
<a name="bp-vars-editable-ranges"></a>
<!-- https://forums.unrealengine.com/showthread.php?65227-Float-Variable-With-Slider-Range-From-C -->
##### 3.2.2.2 ((option:))スライダーと、値の範囲(Slider And Value Ranges) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

すべての `Editable`変数は、その変数に設定されては _ならない_ 値が存在する場合、スライダと値の範囲を使用する必要があります。

例：フェンスの支柱を生成するブループリントには、編集可能な変数 `PostsCount` があり、-1の値は意味をなさないでしょう。 範囲フィールドを使用して0を最小値としてマークします。

編集可能な変数が構築スクリプトで使用されている場合は、誤ってエディタをクラッシュさせる大きな値を割り当てることができないように、適切なスライダ範囲が定義されている必要があります。

値の範囲は、値の境界がわかっている場合にのみ定義する必要があります。 Slider Rangeは偶発的な多数の入力を防ぎますが、未定義のValue Rangeを使用するとスライダ範囲外の値を指定することができます。この値は「危険」とみなされますが有効です。

<a name="3.2.3"></a>
<a name="bp-vars-categories"></a>
#### 3.2.3 分類(Categories) ![#](https://img.shields.io/badge/lint-supported-green.svg)

クラスに少数の変数のみがある場合、カテゴリは必須ではありません。

クラスに適度な量の変数（5〜10）がある場合、すべての `Editable`変数にはデフォルト以外のカテゴリが割り当てられます。 一般的なカテゴリは `Config`です。

クラスに多量の変数がある場合、すべての `Editable`変数は、` Config`カテゴリを基本カテゴリとして使用してサブカテゴリに分類する必要があります。 編集不可能な変数は、その使用法を説明する記述的なカテゴリに分類されるべきです。

> パイプ文字 `|`を使ってサブカテゴリを定義することができます。すなわち `Config | Animations`

例：武器クラスの変数セットは、以下のように構成されています:

	|-- Config
	|	|-- Animations
	|	|-- Effects
	|	|-- Audio
	|	|-- Recoil
	|	|-- Timings
	|-- Animations
	|-- State
	|-- Visuals

<a name="3.2.4"></a>
<a name="bp-vars-access"></a>
#### 3.2.4 変数のアクセスレベル(Variable Access Level) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

C++では、変数にはアクセスレベルの概念があります。 Publicは、クラス外のコードが変数にアクセスできることを意味します。 Protectedは、クラスおよびすべての子クラスだけがこの変数に内部的にアクセスできることを意味します。 Privateはこのクラスのみを意味し、この変数には子クラスはアクセスできません。

ブループリントには現在、Protectedのアクセスの制御の概念が定義されていません。

`編集可能` 変数をPublic(公開)変数として扱います。 編集不可能な変数をProtected(保護)変数として扱います。

<a name="3.2.4.1"></a>
<a name="bp-vars-access-private"></a>
##### 3.2.4.1 非公開変数(Private Variables) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

変数が定義されたクラス内でしかアクセスされず、子クラスではないことが分かっている場合を除き、変数をプライベートとしてマークしないでください。 変数が `protected`とマークされるまで、子クラスの使用を制限したいことが絶対に分かっているときは、privateを確保してください。

<a name="3.2.5"></a>
<a name="bp-vars-advanced"></a>
<!-- https://wiki.unrealengine.com/UPROPERTY -->
#### 3.2.5 ((option:))詳細表示(Advanced Display) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

変数を `編集可能` であるが、頻繁には値を変更しない場合は、それを `Advanced Display`をマークするべきです。 これにより、拡張表示矢印をクリックしない限り、変数が非表示になります。

`Advanced Display`オプションを検索するには、詳細表示された変数として変数の詳細一覧に表示されます。

<a name="3.2.6"></a>
<a name="bp-vars-transient"></a>
#### 3.2.6 ((option:))一時変数(Transient Variables) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

`編集可能` でなく、初期値がゼロまたはヌルのすべての変数は、 `Transient` としてマークする必要があります。

一時変数とは、値を保存して読み込む必要がなく、ゼロまたはゼロの初期値を持つ変数です。 これは、実行時まで値がわからない他のオブジェクトやアクタへの参照に役立ちます。

これにより、変数は常にゼロまたはヌルとして初期化され、エディタがこれまでリファレンスを保存できなくなり、ブループリントクラスの保存と読み込みが高速化されます。

<a name="3.2.7"></a>
<a name="bp-vars-savegame"></a>
#### 3.2.7 ((option:))保存変数(SaveGame Variables) ![#](https://img.shields.io/badge/lint-supported-green.svg)

`SaveGame`から派生したクラスの中でのみ変数のSaveGameプロパティを使用してください。 このプロパティは、`SaveGame`クラスがこの値を保存する場合にのみ使用してください。

`SaveGame`と`Transient`をミックス **しないでください**。 これは意味をなさないです。

<a name="3.2.8"></a>
<a name="bp-vars-config"></a>
#### 3.2.8 ((option:))構成変数(Config Variables) ![#](https://img.shields.io/badge/lint-supported-green.svg)

`Config Variable`フラグは使わないでください。 これにより、設計者は ブループリント の動作を制御することが難しくなります。 構成変数は、まれに変更された変数に対してのみC++で使用する必要があります。 それらを `Advanced Advanced Display` 変数と考えてください。

<a name="3.3"></a>
<a name="bp-functions"></a>
### 3.3 関数、イベント、およびイベントディスパッチャ(Functions, Events, and Event Dispatchers) ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

このセクションでは、関数、イベント、およびイベントディスパッチャの作成方法について説明します。特記事項がない限り、関数に適用されるすべてのものがイベントにも適用されます。

<a name="3.3.1"></a>
<a name="bp-funcs-naming"></a>
#### 3.3.1 関数の名前付け

関数、イベント、イベントディスパッチャーの命名は非常に重要です。名前だけに基づいて、機能についてある種の前提が立てられます。例えば：

* それは純粋関数か？
* それは状態情報を取得してるか？
* それはハンドラか？
* それはRPCか？
* その目的は何か？

関数の名前が適切であれば、これらの質問にすべて答えることができます。

<a name="3.3.1.1"></a>
<a name="bp-funcs-naming-verbs"></a>
#### 3.3.1.1 すべての関数は動詞であるべき

すべての関数とイベントは、情報の取得、データの計算、または何かを爆発させるなど、何らかのアクションを実行します。したがって、すべての関数はすべて動詞で始まる必要があります。それらは現時点で可能な限り語られるべきです。それらはまた、関数等が何をしているかについていくつかのコンテキストを持つべきです。

`OnRep` 関数、イベントハンドラ、およびイベントディスパッチャは、このルールの例外です。

良い例：

* `Fire` - Character/Weaponクラスの場合は良い例です、それの持っているコンテキストに即しています。Barrel/Grass/及び他のあいまいなクラスであれば悪い例です。
* `Jump` - Characterクラス中であればい例です、他の場合はコンテキストが必要です。
* `Explode`
* `ReceiveMessage`
* `SortPlayerArray`
* `GetArmOffset`
* `GetCoordinates`
* `UpdateTransforms`
* `EnableBigHeadMode`
* `IsEnemy` - ["Is" は動詞](http://writingexplained.org/is-is-a-verb)

悪い例：

* `Dead` - 死んでいる？これから死ぬのか？
* `Rock`
* `ProcessData` - あいまいで、これらの言葉は何も意味しません。
* `PlayerState` - 名詞はあいまいです。
* `Color` - コンテキストのない動詞、あいまいな名詞。

<a name="3.3.1.2"></a>
<a name="bp-funcs-naming-onrep"></a>
<!-- https://docs.unrealengine.com/latest/JPN/Resources/ContentExamples/Networking/1_4/index.html -->
#### 3.3.1.2  ((option:)) RepNotify関数プロパティは常に `OnRep_Variable` の形式であるべき

通知変数で複製されるすべての関数は、 `OnRep_Variable` の形式でなければなりません。これはBlueprintエディタによって強制されます。ただし、C++ の `OnRep` 関数を記述している場合、それをBlueprintsに公開する際にはこの規則に従ってください。

<a name="3.3.1.3"></a>
<a name="bp-funcs-naming-bool"></a>
#### 3.3.1.3  Boolを返す情報関数は質問形式にするべき

状態を変えず、どんなオブジェクトも更新せず、単に情報、状態、またはboolのyes/noを取得するための関数を書くときには質問形式にするべきです。同時に [動詞規則](#bp-funcs-naming-verbs) にも従うべきです。

これは質問形式でなければ、その関数がアクションを実行し、そのアクションが成功したかどうかを返すと仮定してよいのと同様に非常に重要です。

良い例：

* `IsDead`
* `IsOnFire`
* `IsAlive`
* `IsSpeaking`
* `IsHavingAnExistentialCrisis`
* `IsVisible`
* `HasWeapon` - ["Has" は動詞](http://grammar.yourdictionary.com/parts-of-speech/verbs/Helping-Verbs.html)
* `WasCharging` - ["Was" は "be"の過去形](http://grammar.yourdictionary.com/parts-of-speech/verbs/Helping-Verbs.html) '前のフレーム' または '前の状態' を参照するとき "was" を使用.
* `CanReload` - ["Can" は動詞](http://grammar.yourdictionary.com/parts-of-speech/verbs/Helping-Verbs.html)

悪い例：

* `Fire` - 燃えている？ 発砲するか？ 燃やすのか？
* `OnFire` - 発射のイベントディスパッチャと混同することがあります。
* `Dead` - 死んでいる？これから死ぬのか？
* `Visibility` - 視認出来る？ 可視化する？ 飛行条件の説明？

<a name="3.3.1.4"></a>
<a name="bp-funcs-naming-eventhandlers"></a>
#### 3.3.1.4 イベントハンドラとディスパッチャは `On` で始まるべき

イベントハンドラや、イベントディスパッチなどの関数は、`On` で始まるべきで、続きは [動詞規則](#bp-funcs-naming-verbs) に従ってください。 過去動詞がうまく読めば、動詞は最後に移動するかもしれません。

単語 `On` の[連結語句](http://dictionary.cambridge.org/us/grammar/british-grammar/about-words-clauses-and-sentences/collocation)は、動詞規則に従うことが免除されます。

`Handle` は許されません。'Unreal' では `Handle` の代わりに` On` を使用しますが、他のフレームワークでは `On`の代わりに` Handle` を使う方がよいかもしれません。

良い例：

* `OnDeath` - ゲームの一般的な連結語句
* `OnPickup`
* `OnReceiveMessage`
* `OnMessageRecieved`
* `OnTargetChanged`
* `OnClick`
* `OnLeave`

悪い例：

* `OnData`
* `OnTarget`
* `HandleMessage`
* `HandleDeath`

<a name="3.3.1.5"></a>
<a name="bp-funcs-naming-rpcs"></a>
#### 3.3.1.5 リモートプロシージャコールにはターゲットが前置されるべき

RPCが作成されるたびに、 `Server`、` Client`、または `Multicast`の接頭辞が付いていなければなりません。一切の例外なくです。

接頭辞の後に、関数命名に関する他のすべての規則に従ってください。

良い例：

* `ServerFireWeapon`
* `ClientNotifyDeath`
* `MulticastSpawnTracerEffect`

悪い例：

* `FireWeapon` - 何らかの種類のRPCを示すものではありません。
* `ServerClientBroadcast` - 混乱します。
* `AllNotifyDeath` - ` Multicast` を使用し、決して `All` を使用しないでください。
* `ClientWeapon` - 動詞ではなく、あいまいです。


<a name="3.3.2"></a>
<a name="bp-funcs-return"></a>
<!-- https://answers.unrealengine.com/questions/139959/how-can-i-create-return-node.html -->
#### 3.3.2 すべての関数にReturnノードが必須

すべての関数にReturnノードは必要です。例外はありません。

Returnノードは、関数の実行が終了したことを明示します。Blueprintが `Sequence`、` ForLoopWithBreak`、および逆向きのrerouteノードで満たされる世界では、可読性、メンテナンス、およびデバッグの容易さのために明示的な実行フローが重要です。

Blueprintコンパイラーは実行フローを追うことができ、Returnノードを使用すれば、ハンドルされないReturnまたは不良なフローがコードのブランチにあるかどうかを警告します。

プログラマがfor節を追加したり、forループが完了した後にロジックを追加してループの反復が早期に返ったりするような状況では、コードフローに偶発的なエラーが生じることがあります。 Blueprintコンパイラの警告は、これらの問題のすべてを直ちに警告します。

<a name="3.4"></a>
<a name="bp-graphs"></a>
### 3.4 Blueprintグラフ (Blueprint Graphs)

このセクションでは、すべてのBlueprintグラフに適用される事項について説明します。

<a name="3.4.1"></a>
<a name="bp-graphs-spaghetti"></a>
#### 3.4.1 スパゲティをなくせ

ワイヤーの始点と終点が明確になるように配置しましょう。グラフを理解するためにわざわざ頭の中でワイヤーをほどく必要はありません。以下のセクションでは、スパゲティを減らすことに紙面の多くを割いています。

<a name="3.4.2"></a>
<a name="bp-graphs-align-wires"></a>
<!-- https://answers.unrealengine.com/questions/323566/unreal-engin-why-u-make-me-so-angry.html -->
#### 3.4.2 ノードではなくワイヤーを整列すべき

いつでもノードではなくワイヤーを整列させてください。ノードのサイズとピン位置を常に制御することはできませんが、ノードの位置を制御しすることとそれによりワイヤーを制御することはいつでもできます。真っ直ぐなワイヤーのラインは、フローをわかりやすくします。凸凹に波打つワイヤーのラインはひどくわかりにくいです。BPノードを選択してStraigten Connectionsコマンドを使用することにより、ワイヤを真っ直ぐにすることができます。Hotkey: Q

良い例：ノードの上部は、白い実行ワイヤーラインを真っ直ぐに維持するためにずらしてあります。
![Aligned By Wires](https://github.com/allar/ue4-style-guide/raw/master/images/bp-graphs-align-wires-good.png "ワイヤによって整列")

悪い例：ノードの上端が一直線に並んでいますが、白い実行ワイヤーラインが凸凹に波打っています。
![Bad](https://github.com/allar/ue4-style-guide/raw/master/images/bp-graphs-align-wires-bad.png "凸凹に波打つ")

許容可能な例：特定のノードは、アラインメントツールの使い方にかかわらずうまく機能しないかもしれません。このような状況では、ノードをより近くに持っていくことで、凸凹に波打つのを最小限に抑えてください。
![Acceptable](https://github.com/allar/ue4-style-guide/raw/master/images/bp-graphs-align-wires-acceptable.png "受け入れ可能(Acceptable)")

<a name="3.4.3"></a>
<a name="bp-graphs-exec-first-class"></a>
#### 3.4.3 白い実行ワイヤーを最優先にするべき

直線状の白い実行ワイヤーを真っ直ぐにするか、なんらかのデータワイヤーを真っ直ぐにするかが選択肢として与えられたら、いつでも白い実行ワイヤーを真っ直ぐにするべきです。

## Contributors

* [Michael Allar](http://allarsblog.com): [GitHub](https://github.com/Allar), [Twitter](https://twitter.com/michaelallar)
* [CosmoMyzrailGorynych](https://github.com/CosmoMyzrailGorynych)
* [billymcguffin](https://github.com/billymcguffin)
* [akenatsu](https://github.com/akenatsu)

## License

Copyright (c) 2016 Gamemakin LLC

See [LICENSE](/LICENSE)

**[⬆ Back to Top](#table-of-contents)**


## Amendments

このガイドをフォークし、チームのスタイルガイドに合わせてルールを変更することをお勧めします。 以下に、スタイルガイドのいくつかの修正案を挙げることができます。 これにより、マージの競合に対処することなく、スタイルガイドを定期的に更新することができます。

# };
