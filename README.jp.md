# [Gamemakin](https://gamemak.in) UE4 Style Guide() {

*Unreal Engine 4 への最も合理的なアプローチ*

[Airbnb Javascript Style Guide](https://github.com/airbnb/javascript) に大きな影響を受けています。

[![Analytics](https://ga-beacon.appspot.com/UA-80567399-1/repo?useReferrer)](#) ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

## Unreal Engine 4 Linter Plugin

このスタイルガイドに対してプロジェクトをチェックする自動化された方法は、[the Unreal Engine marketplace](https://www.unrealengine.com/marketplace/linter) で購入できます。 このプラグインのソースコードは最終的に無料になりますが、ソースコードからエンジンを構築せずにUE4で使用するには、マーケットプレイス版を使用してください。

## 本ドキュメントへリンクする場合

このスタイルガイドの各セクションは、簡単な参照と簡単なリンクのために番号が付けられています。 http://ue4.style の最後にハッシュタグとセクション番号を付加するだけで、任意のセクションに直接リンクすることができます
たとえば、このスタイルガイドの第1原則に誰かを送りたい場合は、http：//ue4.style#0.1という結果になる `＃0.1` を追加します。

## Forks と翻訳

このレポへのプルリクエストに適していない注目すべきフォークまたは翻訳を行った場合は、ここにフォークまたは翻訳を追加するプルリクエストを提出してください。

* [Korean Translation](https://github.com/ymkim50/ue4-style-guide/blob/master/README_Kor.md) by ymkim50
* [Russian Translation](https://github.com/CosmoMyzrailGorynych/ue4-style-guide-rus/blob/master/README.md) by CosmoMyzrailGorynych

## 重要用語

<a name="terms-level-map"></a>
##### Levels/Maps

'map' という語は一般に、平均的な人が'level'と呼んでいるものを指し、互換的に使用することができます。この用語の歴史については[こちら](https://en.wikipedia.org/wiki/Level_(video_gaming))を参照してください。

<a name="terms-cases"></a>
##### Cases

物事に名前を付ける方法はいくつかあります。 いくつかの一般的なケーシングタイプがあります:

> ###### PascalCase
>
> すべての単語を大文字にし、スペースをすべて削除します。, e.g. `DesertEagle`, `StyleGuide`, `ASeriesOfWords`.
> 
> ###### camelCase
>
> 最初の文字は常に小文字ですが、その後のすべての単語は大文字で始まります。, e.g. `desertEagle`, `styleGuide`, `aSeriesOfWords`.
>
> ###### Snake_case
>
> 単語は任意に大文字または小文字を開始できますが、単語はアンダースコアで区切られます。, e.g. `desert_Eagle`, `Style_Guide`, `a_Series_of_Words`.


<a name="0"></a>
## 0. 原則

これらの原則は[idomatic.js style guide](https://github.com/rwaldron/idiomatic.js/)に即します。

<a name="0.1"></a>
### 0.1 あなたのUE4プロジェクトにすでにスタイルガイドがある場合は、それに従ってください。

既存のスタイルガイドがあるチームまたはプロジェクトで作業している場合は、それを尊重する必要があります。 既存のスタイルガイドとこのガイドとの間に矛盾がある場合は、既存のスタイルガイドに従わなくてはなりません。

スタイルガイドは生き生きしたドキュメントでなければなりません。すべての用途に変更のメリットがあると感じる場合は、既存のスタイルガイドとこのガイドのスタイルガイドの変更を提案する必要があります。

> #### "スタイル上の議論は無意味です。スタイルガイドが必要です。それに従うべきです"
> [_Rebecca Murphey_](https://rmurphey.com)

<a name="0.2"></a>
### 0.2 すべてのUnreal Engine 4プロジェクトの構造、アセット、およびコードは、どれだけの人が貢献しても、1人の人が作成したように見えるはずです。

あるプロジェクトから別のプロジェクトに移っても、スタイルや構造を再学習してはいけません。 スタイルガイドに従うことで、不必要な推測やあいまいがなくなります。

また、スタイルについて考える必要もなく、指示に従うだけで、より生産的な作成と保守が可能です。 このスタイルガイドはベストプラクティスを念頭に置いて書かれています。つまり、このスタイルガイドに従って、問題を追跡するのを最小限に抑えることができます。

<a name="0.3"></a>
### 0.3 友人は友人に悪いスタイルをさせません。

スタイルガイドまたはスタイルガイドなしのいずれかで作業している人がいる場合は、修正するようにしてください。

チーム内で働いたり、[Unreal Slackers](http://join.unrealslackers.org/) などのコミュニティで議論するときは、一貫性があるときに助けて助けを求めるのがはるかに簡単です。 誰も、誰かのblueprintsスパゲッティを解くのを手伝ったり、理解できない名前の資産を扱ったりするのを好む人はいません。

あなたの仕事の人が異なるが、一貫性があり、正真正銘のスタイルガイドに従うのを手助けしているなら、あなたはそれに適応できるはずです。 スタイルガイドに準拠していない場合は、ここで指示してください。

<a name="0.4"></a>
### 0.4 スタイルガイドのないチームは私のチームではありません。

Unreal Engine 4チームに参加するときは、最初の質問の1つが「あなたはスタイルガイドを持っていますか？」でなければなりません。 答えがノーなら、あなたはチームとして働く能力について懐疑的でなければなりません。

<a name="toc"></a>
## 目次

> 1. [Asset Naming Conventions](#anc)
> 1. [Directory Structure](#structure)
> 1. [Blueprints](#bp)

<a name="anc"></a>
<a name="1"></a>
## 1. アセットの命名規則 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

命名規則は法律として扱うべきです。 命名規則に準拠したプロジェクトでは、アセットの管理、検索、解析、維持管理が非常に簡単です。

ほとんどのものに接頭辞が付いています。接頭辞は一般的にアセットタイプの略語で、その後にアンダースコアが続きます。

<a name="base-asset-name"></a>
<a name="1.1"></a>
### 1.1 基本アセット名 - `Prefix_BaseAssetName_Variant_Suffix` ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

すべてのアセットに _Base Asset Name_ が必要です。基本資産名は、関連する資産の論理的なグループを表します。この論理グループの一部である資産は、 `Prefix_BaseAssetName_Variant_Suffix`の標準に従うべきです。

パターン `Prefix_BaseAssetName_Variant_Suffix` を念頭に置いて常識的に使うことは、一般的には良い資産名を保証するのに十分です。各要素に関するいくつかの詳細なルールがあります。

`Prefix`と` Suffix`は、以下の [Asset Name Modifier](#asset-name-modifiers) テーブルを介して、資産タイプによって決定されます。

`BaseAssetName`は、この資産群の文脈に関連した簡単で分かりやすい名前によって決定されるべきです。たとえば、Bobという名前のキャラクターがあった場合、Bobのすべてのアセットは `Base`の` Bob`という名前になります。

独特で特殊な資産のバリエーションの場合、 `Variant` は、資産の基本名のサブセットである資産の論理的なグループ分けを表す簡単で分かりやすい名前のいずれかです。例えば、Bobが複数のスキンを持っていた場合、これらのスキンは `BaseAssetName`として` Bob`を使用しますが、認識可能な `Variant`を含みます。 「Evil」スキンは `Bob_Evil` と呼ばれ、「Retro」スキンは `Bob_Retro` と呼ばれる。

ユニークではあるが一般的な資産のバリエーションでは、 `Variant` は `01` から始まる2桁の数字です。例えば、謎めいた岩石を生成する環境アーティストがいる場合、名前は `Rock_01`、` Rock_02`、 `Rock_03` などとなります。まれな例外を除いて、3桁の変種番号は必要ありません。資産が100以上ある場合は、異なるベース名で複数のバリアント名を使用して整理することを検討する必要があります。

資産バリアントの作成方法に応じて、バリアント名を連結することができます。たとえば、Arch Vizプロジェクトのフロアリングアセットを作成する場合は、`Flooring_Marble_01`, `Flooring_Maple_01`, `Flooring_Tile_Squares_01` などの連鎖変形を含むベース名 `Flooring` を使用する必要があります。

<a name="1.1-examples"></a>
#### 1.1 例

##### 1.1e1 Bob

| Asset Type              | Asset Name                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Skeletal Mesh           | SK_Bob                                                     |
| Material                | M_Bob                                                      |
| Texture (Diffuse/Albedo)| T_Bob_D                                                    |
| Texture (Normal)        | T_Bob_N                                                    |
| Texture (Evil Diffuse)  | T_Bob_Evil_D                                               |

##### 1.1e2 Rocks

| Asset Type              | Asset Name                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Static Mesh (01)        | S_Rock_01                                                  |
| Static Mesh (02)        | S_Rock_02                                                  |
| Static Mesh (03)        | S_Rock_03                                                  |
| Material                | M_Rock                                                     |
| Material Instance (Snow)| MI_Rock_Snow                                               |

### 1.2 アセット名修飾子　![#](https://img.shields.io/badge/lint-supported-green.svg)

アセットの名前を付けるときは、これらのテーブルを使用してアセットの　[Base Asset Name](#base-asset-name)　で使用する接頭辞と接尾辞を決定します。

#### Sections

> 1.2.1 [Most Common](#anc-common)

> 1.2.2 [Animations](#anc-animations)

> 1.2.3 [Artificial Intelligence](#anc-ai)

> 1.2.4 [Blueprints](#anc-bp)

> 1.2.5 [Materials](#anc-materials)

> 1.2.6 [Textures](#anc-textures)

> 1.2.7 [Miscellaneous](#anc-misc)

> 1.2.8 [Paper 2D](#anc-paper2d)

> 1.2.9 [Physics](#anc-physics)

> 1.2.10 [Sound](#anc-sound)

> 1.2.11 [User Interface](#anc-ui)

> 1.2.12 [Effects](#anc-effects)

<a name="anc-common"></a>
<a name="1.2.1"></a>
#### 1.2.1 Most Common ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Level / Map             |            |            | [ <Maps></Maps> フォルダ内に配置するべき.](#2.3) |
| Level (Persistent)      |            | _P         |                                  |
| Level (Audio)           |            | _Audio     |                                  |
| Level (Lighting)        |            | _Lighting  |                                  |
| Level (Geometry)        |            | _Geo       |                                  |
| Level (Gameplay)        |            | _Gameplay  |                                  |
| Blueprint               | BP_        |            |                                  |
| Material                | M_         |            |                                  |
| Static Mesh             | S_ or SM_  |            | どちらか1つだけを選択。 S_ を優先する。        |
| Skeletal Mesh           | SK_        |            |                                  |
| Texture                 | T_         | _?         | [Textures](#anc-textures) を参照してください。   |
| Particle System         | PS_        |            |                                  |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つだけを選択。 WBP_ を優先する。      |

マップと呼ばれるフォルダにある必要があります

<a name="anc-animations"></a>
<a name="1.2.2"></a>
#### 1.2.2 Animations ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Aim Offset              | AO_        |            |                                  |
| Aim Offset 1D           | AO_        |            |                                  |
| Animation Blueprint     | ABP_       |            |                                  |
| Animation Composite     | AC_        |            |                                  |
| Animation Montage       | AM_        |            |                                  |
| Animation Sequence      | A_ or AS_  |            | どちらか1つだけを選択。 A_ を優先する。        |
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

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| AI Controller           | AIC_       |            |                                  |
| Behavior Tree           | BT_        |            |                                  |
| Blackboard              | BB_        |            |                                  |
| Decorator               | BTDecorator_ |          |                                  |
| Service                 | BTService_ |            |                                  |
| Task                    | BTTask_    |            |                                  |

<a name="anc-bp"></a>
<a name="1.2.4"></a>
### 1.2.4 Blueprints ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Blueprint               | BP_        |            |                                  |
| Blueprint Function Library | BPFL_   |            |                                  |
| Blueprint Interface     | BPI_       |            |                                  |
| Blueprint Macro Library | BPML_      |            | 可能な限り、マクロライブライを使うべきでない。 |
| Enumeration             | E          |            | アンダースコアを付けない。                   |
| Structure               | F or S     |            | アンダースコアを付けない。                   |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つだけを選択。 WBP_ を優先する。      |

<a name="anc-materials"></a>
<a name="1.2.5"></a>
### 1.2.5 Materials ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Material                | M_         |            |                                  |
| Material (Post Process) | PP_        |            |                                  |
| Material Function       | MF_        |            |                                  |
| Material Instance       | MI_        |            |                                  |
| Material Parameter Collection | MPC_ |            |                                  |
| Subsurface Profile      | SP_ or SSP_|            | どちらか1つだけを選択。 SP_ を優先する。       |
| Physical Materials      | PM_        |            |                                  |

<a name="anc-textures"></a>
<a name="1.2.6"></a>
### 1.2.6 Textures ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Texture                 | T_         |            |                                  |
| Texture (Diffuse/Albedo/Base Color)| T_ | _D      |                                  |
| Texture (Normal)        | T_         | _N         |                                  |
| Texture (Roughness)     | T_         | _R         |                                  |
| Texture (Alpha/Opacity) | T_         | _A         |                                  |
| Texture (Ambient Occlusion) | T_     | _O or _AO  | どちらか1つだけを選択。 _O を優先する。       |
| Texture (Bump)          | T_         | _B         |                                  |
| Texture (Emissive)      | T_         | _E         |                                  |
| Texture (Mask)          | T_         | _M         |                                  |
| Texture (Specular)      | T_         | _S         |                                  |
| Texture (Packed)        | T_         | _*         | 下記の注記 [packing](#anc-textures-packing) を参照 |
| Texture Cube            | TC_        |            |                                  |
| Media Texture           | MT_        |            |                                  |
| Render Target           | RT_ or RTT_|            | どちらか1つだけを選択。 RT_ を優先する。       |
| Cube Render Target      | RTC_       |            |                                  |
| Texture Light Profile   | TLP        |            |                                  |

<a name="anc-textures-packing"</a>
<a name="1.2.6.1"></a>
#### 1.2.6.1 Texture Packing ![#](https://img.shields.io/badge/lint-unsupported-red.svg)
テクスチャデータの複数のレイヤを1つのテクスチャにパックするのが一般的な方法です。 これの一例は、エミッシブ、ラフネス、アンビエントオクルージョンをテクスチャの赤、緑、青のチャンネルとしてまとめたものです。 接尾辞を決定するには、上の指定された接尾辞の文字を単純にスタックします。 `_ERO`。

> Diffuse/AlbedoのアルファチャンネルにAlpha/Opacityレイヤーを含めることは一般的に受け入れられます。これは一般的な方法で、 `_D` 接尾辞に ` A` を追加することはオプションです。

Diffuse/AlbedoのアルファチャンネルのAlpha/Opacityマスク以外の4チャンネルのデータをテクスチャ（RGBA）にパッキングするのはお勧めできません。

<a name="anc-misc"></a>
<a name="1.2.7"></a>
### 1.2.7 Miscellaneous ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Animated Vector Field   | VFA_       |            |                                  |
| Camera Anim             | CA_        |            |                                  |
| Color Curve             | Curve_     | _Color     |                                  |
| Curve Table             | Curve_     | _Table     |                                  |
| Data Asset              | *_         |            | 接頭辞はクラスに基づいている必要があります。 |
| Data Table              | DT_        |            |                                  |
| Float Curve             | Curve_     | _Float     |                                  |
| Foliage Type            | FT_        |            |                                  |
| Force Feedback Effect   | FFE_       |            |                                  |
| Landscape Grass Type    | LG_        |            |                                  |
| Landscape Layer         | LL_        |            |                                  |
| Matinee Data            | Matinee_   |            |                                  |
| Media Player            | MP_        |            |                                  |
| Object Library          | OL_        |            |                                  |
| Redirector              |            |            | これらはできるだけ早く修正する必要があります。 |
| Sprite Sheet            | SS_        |            |                                  |
| Static Vector Field     | VF_        |            |                                  |
| Touch Interface Setup   | TI_        |            |                                  |
| Vector Curve            | Curve_     | _Vector    |                                  |

<a name="anc-paper2d"></a>
<a name="1.2.8"></a>
### 1.2.8 Paper 2D ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Paper Flipbook          | PFB_       |            |                                  |
| Sprite                  | SPR_       |            |                                  |
| Sprite Atlas Group      | SPRG_      |            |                                  |
| Tile Map                | TM_        |            |                                  |
| Tile Set                | TS_        |            |                                  |

<a name="anc-physics"></a>
<a name="1.2.9"></a>
### 1.2.9 Physics ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Physical Material       | PM_        |            |                                  |
| Physical Asset	  | PHYS_      |            |                                  |
| Destructible Mesh       | DM_        |            |                                  |

<a name="anc-sounds"></a>
<a name="1.2.10"></a>
### 1.2.10 Sounds ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
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

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Font                    | Font_      |            |                                  |
| Slate Brush             | Brush_     |            |                                  |
| Slate Widget Style      | Style_     |            |                                  |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つだけを選択。 WBP_ を優先する。      |

<a name="anc-effects"></a>
<a name="1.2.12"></a>
### 1.2.12 Effects ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Particle System         | PS_        |            |                                  |
| Material (Post Process) | PP_        |            |                                  |

<a name="2"></a>
<a name="structure"></a>
## 2. コンテンツディレクトリの構造 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

アセット名と同様に重要なことに、プロジェクトのディレクトリ構造は法律とみなすべきです。 資産の命名規則とコンテンツディレクトリ構造が両立し、いずれかの違反は不要な混乱の原因となります。

UE4プロジェクトのコンテンツをレイアウトする方法は複数あります。 このスタイルでは、アセットをグループ化する別の共通構造ではなく、特定のタイプのアセットを検索するために、コンテンツブラウザのフィルタリングと検索機能にもっと依存する構造を使用します。

>上の [naming convention](#1.2) を使用している場合、フォルダに `Meshes`, `Textures`, および `Materials`などの類似の型のアセットを格納することは、アセットの型がすでにソートされているため、 プレフィックスだけでなく、コンテンツブラウザでフィルタリングすることができます。


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

The reasons for this structure are listed in the following sub-sections.

### 章

> 2.1 [Folder Names](#structure-folder-names)

> 2.2 [Top-Level Folders](#structure-top-level)

> 2.3 [Developer Folders](#structure-developers)

> 2.4 [Maps](#structure-maps)

> 2.5 [Core](#structure-core)

> 2.6 [`Assets` and `AssetTypes`](#structure-assettypes)

> 2.7 [Large Sets](#structure-large-sets)

> 2.8 [Material Library](#structure-material-library)


<a name="2.1"></a>
<a name="structure-folder-names"><a>
### 2.1  フォルダ名 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

これらは、コンテンツ構造内の任意のフォルダに名前を付ける一般的な規則です。

<a name="2.1.1"></a>
#### 2.1.1 常に PascalCase を使用 [<sup>*</sup>](#terms-cases) ![#](https://img.shields.io/badge/lint-supported-green.svg)

PascalCaseは、大文字で名前を始めることを意味し、スペースを使用する代わりに、すべての次の単語も大文字で始まります。 たとえば、`DesertEagle`, `RocketPistol`,および`ASeriesOfWords` などです。

See [Cases](#terms-cases).

<a name="2.1.2"></a>
#### 2.1.2 決してスペースを使用しないでください ![#](https://img.shields.io/badge/lint-supported-green.svg)

[2.1.1](#2.1.1) を再実施し、決してスペースを使用しないでください。 スペースによって、さまざまなエンジニアリングツールやバッチ処理が失敗する可能性があります。 理想的には、プロジェクトのルートには空白が含まれておらず、 `C:\Users\My Name\My Documents\Unreal Projects` の代わりに `D:\Project`のような場所に置かれているのが理想的です。

<a name="2.1.3"></a>
#### 2.1.3 Unicode文字とその他の記号を使用しないでください ![#](https://img.shields.io/badge/lint-supported-green.svg)

あなたのゲームキャラクターの名前が「Zoë」の場合、そのフォルダー名は `Zoe`でなければなりません。 Unicode文字はエンジニアリングツールの [Spaces](#2.1.2) より悪くなり、UE4の一部ではパス内のUnicode文字もサポートされません。

これに関連して、プロジェクトに [説明できない問題](https://answers.unrealengine.com/questions/101207/undefined.html) があり、コンピュータのユーザー名がUnicode文字（つまり、あなたの名前は `Zoë`）である場合、 あなたの `My Documents`フォルダにあるプロジェクトはこの問題を抱えています。 単にプロジェクトを `D:\Project`のようなものに移動するだけで、これらの不思議な問題が修正されます。

`@`, `-`, `_`, `,`, `*`, と `#` のような `a-z`, `A-Z`, 及び `0-9` 以外の文字を使うと、 他のプラットフォーム、ソース管理、および弱いエンジニアリングツールの問題を追跡することは困難です。

<a name="2.2"></a>
<a name="structure-top-level"><a>
### 2.2 プロジェクト固有アセットのためにトップレベルフォルダを使用 ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのプロジェクトのアセットは、プロジェクトの名前を付けたフォルダに存在する必要があります。 たとえば、プロジェクトの名前が「Generic Shooter」の場合、そのコンテンツの _全て_ は `Content/GenericShooter` 以下に存在する必要があります。

> `Developers` フォルダはあなたのプロジェクトが依存している資産のためではなく、したがってプロジェクト特有のものではありません。 これに関する詳細については、 [2.2](#2.2) を参照してください。

このアプローチには複数の理由があります。

<a name="2.2.1"></a>
#### 2.2.1 グローバルアセットなし

多くの場合、コードスタイルガイドでは、グローバル名前空間を汚染しないように書かれています。これは同じ原則に従います。 資産がプロジェクトフォルダの外に存在することが許される場合、フォルダ内にない資産が資産を整理する必要がないという悪い行為を促すため、厳密な構造レイアウトを強制するのはずっと困難になります。

すべての資産は目的を持っている必要があります。そうでなければ、プロジェクトに属していません。 アセットが実験的なテストであり、プロジェクトで使用すべきでない場合は、 [`Developer`](#2.3) フォルダーに置く必要があります。 

<a name="2.2.2"></a>
#### 2.2.2 移行での衝突の削減

複数のプロジェクトに取り組んでいるときに、チームが両方のプロジェクトに役立つものを作っていれば、あるプロジェクトから別のプロジェクトに資産をコピーするのが一般的です。これが発生すると、コピーを実行する最も簡単な方法は、コンテンツブラウザの移行機能を使用して、選択したアセットだけでなくそのすべての依存関係をコピーするためです。

これらの依存関係は、簡単に問題を引き起こす可能性があります。 2つのプロジェクトの資産にトップレベルのフォルダがなく、すでに名前が付けられている、または以前に移行されたアセットがある場合、新しい移行によって誤って既存のアセットの変更が消去される可能性があります。

これはまた、EpicのMarketplaceスタッフが提出された資産に対して同じポリシーを強制する主な理由です。

移行後、コンテンツブラウザの 'Replace References' ツールを使用して資産の安全なマージを行うことができ、プロジェクトの最上位フォルダに属していない資産の明確な明示が併合を保留しています。アセットがマージされ、完全に移行されると、コンテンツツリーに別のトップレベルのフォルダは存在しないはずです。この方法は、完全に安全に実行される移行を保証するために _100％_ 保証されています。

<a name="2.2.2e1"></a>
##### 2.2.2e1 マスターマテリアルの例

たとえば、あるプロジェクトに別のプロジェクトで使用したいマスター素材を作成し、その資産を移行したとします。このアセットがトップレベルのフォルダにない場合、 `Content/MaterialLibrary/M_Master` のような名前を持つ可能性があります。ターゲットプロジェクトにすでにマスタマテリアルがない場合、これは問題なく動作するはずです。

一方または両方のプロジェクトの作業が進行するにつれて、それぞれのマスター資料は、通常の開発過程のために、特定のプロジェクトに合わせて変更される可能性があります。

たとえば、あるプロジェクトのアーティストが静的メッシュの包括的なモジュラーセットを作成し、誰かがその静的メッシュのセットを2番目のプロジェクトに含める場合など、問題が発生します。アセットを作成したアーティストが、指示されているとおりに `Content/MaterialLibrary/M_Master` に基づいて素材インスタンスを使用した場合、移行が実行されると、以前に移行された `Content/MaterialLibrary/M_Master` アセット。

この問題は、予測するのが難しく、説明するのが難しい場合があります。静的メッシュを移動する人は、プロジェクトのマスターマテリアルの開発に精通している人と同じ人ではないかもしれませんし、問題の静的メッシュがマスターマテリアルに依存しているマテリアルインスタンスに依存していることに気づいていないかもしれません。しかし、Migrateツールでは、依存関係のチェーン全体が機能する必要があるため、これらのアセットを他のプロジェクトにコピーするときに `Content/MaterialLibrary/M_Master`を強制的に取得し、既存のアセットを上書きします。

この時点で、両方のプロジェクトのマスタマテリアルが互換性がない場合は、プロジェクトのマテリアルライブラリ全体が破損する危険性があります。アセットが保存されていないため、すでに移行されている可能性のあるその他の依存関係トップレベルのフォルダ。静的メッシュの単純な移行は、現在非常に醜い作業になります。

<a name="2.2.3"></a>
#### 2.2.3 サンプル、テンプレート、マーケットプレイスのコンテンツはリスクフリーです

[2.2.2](#2.2.2) の拡張版では、チームメンバーがサンプルコンテンツ、テンプレートファイル、または市場から購入した資産を追加することを決定した場合、これらの新しい資産がプロジェクトの妨げにならないことが保証されます プロジェクトの最上位のフォルダに一意の名前が付けられていない限り、

マーケットプレイスのコンテンツを [トップレベルのフォルダルール](#2.2) に完全に準拠させることはできません。 トップレベルのフォルダに大部分のコンテンツを持つ多くのアセットが存在しますが、Epicのサンプルコンテンツやグローバルな `Content` フォルダを汚染するレベルファイルも変更されている可能性があります。

[2.2](#2.2) を遵守する場合、マーケットプレイスの競合は、2つのマーケットプレイス資産のEpicサンプルコンテンツが同じである場合に起こります。 すべての資産がプロジェクト固有のフォルダに含まれている場合、フォルダに移動した可能性があるサンプルコンテンツが含まれていれば、プロジェクトは中断しません。

#### 2.2.4 DLC、サブプロジェクト、およびパッチは容易に維持されます

DLCをリリースする予定のプロジェクト、または複数のサブプロジェクトが関連付けられている場合、これらのプロジェクトは移行されるか、単にビルドされないことがあります。これらのプロジェクトに関連するアセットには、独自のトップレベルコンテンツフォルダが必要です。 これにより、DLCはメインプロジェクトのコンテンツとは別に料理がはるかに簡単になります。 サブプロジェクトは、最小限の労力で入退出することもできます。 アセットの素材を変更したり、パッチで非常に特殊なアセットオーバーライド動作を追加する必要がある場合は、これらの変更をパッチフォルダに簡単に入れて、コアプロジェクトを壊すことなく安全に作業できます。

<a name="2.3"></a>
<a name="structure-developers"></a>
### 2.3 ローカルテスト用にDevelopersフォルダを使用してください ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

プロジェクトの開発中に、チームメンバーがコアプロジェクトを危険にさらすことなく自由に実験できる「サンドボックス」を持つことは非常に一般的です。この作業が進行中である可能性があるため、これらのチームメンバはプロジェクトのソース管理サーバーに資産を配置することができます。すべてのチームがデベロッパーフォルダの使用を必要とするわけではありませんが、それらを使用するチームはソース管理に提出された資産に共通の問題に遭遇することがよくあります。

チームメンバーが、使用準備が整っていない資産を誤って使用することは非常に簡単で、その資産が削除されると問題が発生する可能性があります。たとえば、アーティストが静的メッシュのモジュラセットを反復処理していて、サイジングとグリッドのスナッピングが正しく行われているとします。世界の建築家がこれらの資産をメインプロジェクトフォルダに見た場合、彼らは信じられないほどの変更や削除を受ける可能性があることを知らずに、レベル全体でそれらの資産を使用するかもしれません。これにより、チームの全員が大量の再作業を行うことになります。

これらのモジュラーアセットがDeveloperフォルダに配置されている場合、世界の建築家は決してそれらを使用する理由があってはならず、問題は起こりません。コンテンツブラウザには、デベロッパーフォルダを非表示にする特定の表示オプションがあります（デフォルトでは非表示になっています）ので、通常の使用状態で誤ってデベロッパーアセットを使用することはできません。

アセットを使用できるようになると、アーティストはアセットをプロジェクト固有のフォルダに移動し、リダイレクタを修正するだけです。これは本質的に資産を実験から生産に「促進」しています。

<a name="2.4"></a>
<a name="structure-maps"></a>
### 2.4 すべてのMap[<sup>*</sup>](#terms-level-map) ファイルは、マップと呼ばれるフォルダに所属しています ![#](https://img.shields.io/badge/lint-supported-green.svg)

Map ファイルは信じられないほど特殊で、特にサブレベルやストリーミングレベルで作業する場合は、すべてのプロジェクトで独自のマップ命名システムを使用するのが一般的です。特定のプロジェクトでどのようなマップ体系が整っていても、すべてのレベルは `/Content/Project/Maps` に属している必要があります。

場所を説明することなく特定の地図を開くように誰かに指示できることは、時間の節約と一般的な「クオリティ・オブ・ライフ」改善です。 `Maps/Campaign1/`や `Maps/Arenas`のように、レベルが`Maps`のサブフォルダ内にあるのが一般的ですが、ここで最も重要なのは  `/Content/Project/Maps`。

これにより、エンジニア向けの調理作業も簡単になります。ビルドプロセスのレベルを狂わせることは、それらのために任意のフォルダを掘り下げなければならない場合、非常に不快になります。チームの地図がすべて1か所にある場合、誤ってビルド内の地図を調理するのはずっと難しくなります。また、QAプロセスだけでなくビルドスクリプトも簡単に作成できます。

<a name="2.5"></a>
<a name="structure-core"></a>
### 2.5 重要なBlueprintsやその他の資産のための `Core`フォルダを使用してください ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

プロジェクトの動作に不可欠な資産に `/Content/Project/Core`フォルダを使用してください。たとえば、 `GameMode`、` Character`、 `PlayerController`、` GameState`、 `PlayerState`、および関連するBlueprintsはここに住んでいなければなりません。

これにより、他のチームメンバーにとって非常に明確な「これらに触れないでください」というメッセージが作成されます。非エンジニアは `Core`フォルダに入る理由はほとんどありません。優れたコード構造スタイルに従えば、デザイナーは、機能を公開する子クラスでゲームプレイを調整する必要があります。世界の建築家は、潜在的に悪用されるベースクラスではなく、指定されたフォルダでプレハブブループリントを使用する必要があります。

たとえば、プロジェクトがレベルに配置できるピックアップを必要とする場合、ピックアップの基本動作を定義する基本ピックアップクラスが `Core/Pickups` に存在するはずです。 Health または Ammoなどの特定のピックアップは、`/Content/Project/Placeables/Pickups/`のようなフォルダに存在するはずです。ゲームデザイナーはこのフォルダ内のピックアップを定義し調整することができますが、プロジェクト全体のピックアップを意図せず破損する可能性があるため、`Core/Pickups` に触れてはいけません。

<a name="2.6"></a>
<a name="structure-assettypes"></a>
### 2.6 `Assets`または` AssetTypes`と呼ばれるフォルダを作成しないでください ![#](https://img.shields.io/badge/lint-supported-green.svg)

<a name="2.6.1"></a>
#### 2.6.1 `Assets`という名前のフォルダを作成することは冗長です ![#](https://img.shields.io/badge/lint-supported-green.svg)

全てのアセットはアセットです。   

<a name="2.6.2"></a>
#### 2.6.2 `Meshes`、` Textures`、または `Materials`という名前のフォルダを作成することは冗長です ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのアセット名は、そのアセットタイプを念頭に置いて命名されます。これらのフォルダは冗長な情報のみを提供し、これらのフォルダの使用は、コンテンツブラウザが提供する堅牢で使いやすいフィルタリングシステムで簡単に置き換えることができます。

 `Environment/Rocks/` に静的メッシュだけを表示したいですか？静的メッシュフィルターをオンにするだけです。すべてのアセットの名前が正しく指定されている場合は、接頭辞に関係なくアルファベット順にソートされます。静的メッシュとスケルトンメッシュの両方を表示したいですか？両方のフィルターをオンにするだけです。これにより、コンテンツブラウザのツリービューで2つのフォルダを `Control-Click` する必要がなくなります。

> これはまた、資産の完全なパス名をほとんど利益のために拡張します。静的メッシュの `S_` 接頭辞は2文字だけですが、` Meshes/`は7文字です。

これをしないと、誰かが静的メッシュやテクスチャを `Materials`フォルダに置くことを避けることができなくなります。

<a name="2.7"></a>
<a name="structure-large-sets"></a>
### 2.7 非常に大きなアセットのセットは、それら独自のフォルダレイアウトを取ります ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

これは、 [2.6](#2.6) の擬似例外として見ることができます。

各資産に独自の目的がある膨大な量の関連ファイルを持つ特定の資産タイプがあります。 最も一般的な2つは、アニメーションとオーディオのアセットです。 一緒に属しているこれらの資産が15以上あることが判明した場合、それらは一緒になっている必要があります。

たとえば、複数の文字にまたがって共有されるアニメーションは、`Characters/Common/Animations` にあり、`Locomotion` や `Cinematic` などのサブフォルダを持つことがあります。

> テクスチャや素材などのアセットには適用されません。 大量の岩石がある場合、 `Rocks` フォルダーは大量のテクスチャーを持つのが一般的ですが、これらのテクスチャーは一般的には特定の岩石にしか関連しておらず、適切に名前を付ける必要があります。 これらのテクスチャが [Material Library](#2.8) の一部であっても

<a name="2.8"></a>
<a name="structure-material-library"></a>
### 2.8 `MaterialLibrary` ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

プロジェクトでマスター素材、レイヤード素材、または資産のサブセットに属しない再利用可能な素材やテクスチャを使用する場合、これらの資産は `Content/Project/MaterialLibrary` に配置する必要があります。

このようにして、すべての「グローバル」マテリアルは生きる場所を持ち、簡単に見つけられます。

> これにより、プロジェクト内で「材料インスタンスのみ使用」ポリシーを実行することも非常に簡単になります。すべてのアーティストとアセットがマテリアルインスタンスを使用する必要がある場合は、存在するはずの正規のアセットのみがこのフォルダ内にあります。 `MaterialLibrary` 以外のフォルダ内のベースマテリアルを検索することで、これを簡単に確認できます。

`MaterialLibrary` は、純粋にマテリアルである必要はありません。共有ユーティリティテクスチャ、マテリアル関数、およびこのようなその他のものは、意図した目的を指定するフォルダ内にここに格納する必要があります。例えば、一般的なノイズテクスチャは `MaterialLibrary/Utility` に置かなければなりません。

テストやデバッグのためのマテリアルは `MaterialLibrary/Debug` の中になければなりません。これにより、出荷前にデバッグマテリアルをプロジェクトから簡単に取り除くことができ、参照エラーが表示されている場合に生産アセットがそれらを使用している場合、信じられないほど明らかになります。

<a name="3"></a>
<a name="bp"></a>
## 3. Blueprints ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

このセクションでは、Blueprintのクラスとその内部について説明します。 可能であれば、スタイルルールは [Epic's Coding Standard](https://docs.unrealengine.com/latest/INT/Programming/Development/CodingStandard) に準拠しています。

### 章

> 3.1 [Compiling](#bp-compiling)

> 3.2 [Variables](#bp-vars)

<a name="3.1"></a>
<a name="bp-compiling"></a>
### 3.1 Compiling ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのblueprintsは、ゼロの警告とゼロのエラーでコンパイルする必要があります。 非常に恐ろしい予期しない動作に急速にカスケードするので、blueprintsの警告とエラーを直ちに修正する必要があります。

破損したblueprintsをソース管理に提出しない*。 それらをソース管理に保存する必要がある場合は、代わりにそれらをシェルフしてください。

壊れたblueprintsは、壊れた参照、予期しない動作、料理の失敗、頻繁な不要な再コンパイルなど、別の方法で現れる問題を引き起こす可能性があります。 壊れたblueprintsはあなたのゲーム全体を破壊する力を持っています。

<a name="3.2"></a>
<a name="bp-vars"></a>
### 3.2 Variables ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

#### Sections

> 3.2.1 [Naming](#bp-vars)

> 3.2.2 [Editable](#bp-vars-editable)

> 3.2.3 [Categories](#bp-vars-categories)

> 3.2.4 [Access](#bp-vars-access)

> 3.2.5 [Advanced](#bp-vars-advanced)

> 3.2.6 [Transient](#bp-vars-transient)

> 3.2.7 [SaveGame](#bp-vars-savegame)

> 3.2.8 [Config](#bp-vars-config)

<a name="3.2.1"></a>
<a name="bp-var-naming"></a>
#### 3.2.1 Naming ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

<a name="3.2.1.1"></a>
<a name="bp-var-naming-nouns"></a>
##### 3.2.1.1 Nouns ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

すべての非ブール変数名は、明確で明確で説明的な名詞でなければなりません。

<a name="3.2.1.2"></a>
<a name="bp-var-naming-case"></a>
##### 3.2.1.2 PascalCase ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべての非ブール変数は [PascalCase](#terms-cases) の形式でなければなりません。

<a name="3.2.1.2e"></a>
###### 3.2.1.2e Examples:

* `Score`
* `Kills`
* `TargetPlayer`
* `Range`
* `CrosshairColor`
* `AbilityID`

<a name="3.2.1.3"></a>
<a name="bp-var-bool-prefix"></a>
##### 3.2.1.3 Boolean `b` Prefix ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのブール値はPascalCaseで指定する必要がありますが、先頭に小文字の `b` を付けます。

例： `Dead`と` Evil` **ではなく**、 `bDead`と` bEvil`を使います。

UE4 Blueprint editors は、変数の使いやすい表示に `b`を含めないことを知っています。

<a name="3.2.1.4"></a>
<a name="bp-var-bool-names"></a>
##### 3.2.1.4 Boolean Names ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

<a name="3.2.1.4.1"></a>
###### 3.2.1.4.1 General And Independent State Information ![#](https://img.shields.io/badge/lint-supported-green.svg)

すべてのブール値は、一般的な情報を表すならば可能なときには記述的形容詞として命名されるべきである。 その変数を疑問として含む単語、例えば `Is`を含めないでください。 これは関数用に予約されています。

例： `bDead`と` bHostile` **ではなく**、 `bIsDead`と` bIsHostile`を使います。

`bRunning`のような動詞を使わないようにしてください。 動詞は複雑な状態につながる傾向があります。

<a name="3.2.1.4.2"></a>
###### 3.2.1.4.2 Complex States ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

複合および/または従属状態を表すためにブール値を使用しないでください。 これにより、状態の追加と削除が複雑になり、もはや簡単には読み込めなくなります。 代わりに列挙を使用してください。

例：武器を定義するときに、武器を再装備したり装備することが**できない場合は**、 bReloadingを使用せず、bEquippingを使用しないでください。 `EWeaponState`という名前の列挙体を定義し、代わりに` WeaponState`という名前のこの型の変数を使用してください。 これにより、武器に新しい状態を追加することがはるかに容易になります。

例： `bWalking`や` bSprinting`が必要な場合は `Root`を**使わないでください**。 これは、明確に定義された状態名を持つ列挙として定義する必要があります。

<a name="3.2.1.5"></a>
<a name="bp-vars-naming-context"></a>
##### 3.2.1.5 Considered Context ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Blueprintのすべての変数参照は常にコンテキストを持つので、すべての変数名はコンテキストと重複してはいけません。

<a name="3.2.1.5e"></a>
###### 3.2.1.5e Examples:

`BP_PlayerCharacter`というBlueprintを考えてみましょう。

**Bad**

* `PlayerScore`
* `PlayerKills`
* `MyTargetPlayer`
* `MyCharacterName`
* `CharacterSkills`
* `ChosenCharacterSkin`

これらの変数はすべて重複して名前が付けられます。 これらの変数を定義しているのは `BP_PlayerCharacter`なので、変数はその変数が属する` BP_PlayerCharacter`を表しています。

**Good**

* `Score`
* `Kills`
* `TargetPlayer`
* `Name`
* `Skills`
* `Skin`

<a name="3.2.1.6"></a>
<a name="bp-vars-naming-atomic"></a>
##### 3.2.1.6 Do _Not_ Include Atomic Type Names ![#](https://img.shields.io/badge/lint-supported-green.svg)

Atomic or primitive variables are variables that represent data in their simplest form, such as booleans, integers, floats, and enumerations.

Strings and vectors are considered atomic in terms of style when working with Blueprints, however they are technically not atomic.

> While vectors consist of three floats, vectors are often able to be manipulated as a whole, same with rotators.

> Do _not_ consider Text variables as atomic, they are secretly hiding localization functionality. The atomic type of a string of characters is `String`, not `Text`.

Atomic variables should not have their type name in their name.

Example: Use `Score`, `Kills`, and `Description` **not** `ScoreFloat`, `FloatKills`, `DescriptionString`.

The only exception to this rule is when a variable represents 'a number of' something to be counted _and_ when using a name without a variable type is not easy to read.

Example: A fence generator needs to generate X number of posts. Store X in `NumPosts` or `PostsCount` instead of `Posts` as `Posts` may potentially read as an Array of a variable type named `Post`.

<a name="3.2.1.7"></a>
<a name="bp-vars-naming-complex"></a>
##### 3.2.1.7 Do Include Non-Atomic Type Names ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Non-atomic or complex variables are variables that represent data as a collection of atomic variables. Structs, Classes, Interfaces, and primitives with hidden behavior such as `Text` and `Name` all qualify under this rule.

> While an Array of an atomic variable type is a list of variables, Arrays do not change the 'atomicness' of a variable type.

These variables should include their type name while still considering their context.

If a class owns an instance of a complex variable, i.e. if a `BP_PlayerCharacter` owns a `BP_Hat`, it should be stored as the variable type as without any name modifications.

Example: Use `Hat`, `Flag`, and `Ability` **not** `MyHat`, `MyFlag`, and `PlayerAbility`.

If a class does not own the value a complex variable represents, you should use a noun along with the variable type.

Example: If a `BP_Turret` has the ability to target a `BP_PlayerCharacter`, it should store its target as `TargetPlayer` as when in the context of `BP_Turret` it should be clear that it is a reference to another complex variable type that it does not own.


<a name="3.2.1.8"></a>
<a name="bp-vars-naming-arrays"></a>
##### 3.2.1.8 Arrays ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

Arrays follow the same naming rules as above, but should be named as a plural noun.

Example: Use `Targets`, `Hats`, and `EnemyPlayers`, **not** `TargetList`, `HatArray`, `EnemyPlayerArray`.


<a name="3.2.2"></a>
<a name="bp-vars-editable"></a>
#### 3.2.2 Editable Variables ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

All variables that are safe to change the value of in order to configure behavior of a blueprint should be marked as `Editable`.

Conversely, all variables that are not safe to change or should not be exposed to designers should _not_ be marked as editable, unless for engineering reasons the variable must be marked as `Expose On Spawn`.

Do not arbitrarily mark variables as `Editable`.

<a name="3.2.2.1"></a>
<a name="bp-vars-editable-tooltips"></a>
##### 3.2.2.1 Tooltips ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All `Editable` variables, including those marked editable just so they can be marked as `Expose On Spawn`, should have a description in their `Tooltip` fields that explains how changing this value affects the behavior of the blueprint.

<a name="3.2.2.2"></a>
<a name="bp-vars-editable-ranges"></a>
##### 3.2.2.2 Slider And Value Ranges ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All `Editable` variables should make use of slider and value ranges if there is ever a value that a variable should _not_ be set to.

Example: A blueprint that generates fence posts might have an editable variable named `PostsCount` and a value of -1 would not make any sense. Use the range fields to mark 0 as a minimum.

If an editable variable is used in a Construction Script, it should have a reasonable Slider Range defined so that someone can not accidentally assign it a large value that could crash the editor.

A Value Range only needs to be defined if the bounds of a value are known. While a Slider Range prevents accidental large number inputs, an undefined Value Range allows a user to specify a value outside the Slider Range that may be considered 'dangerous' but still valid.

<a name="3.2.3"></a>
<a name="bp-vars-categories"></a>
#### 3.2.3 Categories ![#](https://img.shields.io/badge/lint-supported-green.svg)

If a class has only a small number of variables, categories are not required.

If a class has a moderate amount of variables (5-10), all `Editable` variables should have a non-default category assigned. A common category is `Config`.

If a class has a large amount of variables, all `Editable` variables should be categorized into sub-categories using the category `Config` as the base category. Non-editable variables should be categorized into descriptive categories describing their usage. 

> You can define sub-categories by using the pipe character `|`, i.e. `Config | Animations`.

Example: A weapon class set of variables might be organized as:

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
#### 3.2.4 Variable Access Level ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

In C++, variables have a concept of access level. Public means any code outside the class can access the variable. Protected means only the class and any child classes can access this variable internally. Private means only this class and no child classes can access this variable.

Blueprints do not have a defined concept of protected access currently.

Treat `Editable` variables as public variables. Treat non-editable variables as protected variables.

<a name="3.2.4.1"></a>
<a name="bp-vars-access-private"></a>
##### 3.2.4.1 Private Variables ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Unless it is known that a variable should only be accessed within the class it is defined and never a child class, do not mark variables as private. Until variables are able to be marked `protected`, reserve private for when you absolutely know you want to restrict child class usage.

<a name="3.2.5"></a>
<a name="bp-vars-advanced"></a>
#### 3.2.5 Advanced Display ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

If a variable should be editable but often untouched, mark it as `Advanced Display`. This makes the variable hidden unless the advanced display arrow is clicked.

To find the `Advanced Display` option, it is listed as an advanced displayed variable in the variable details list.

<a name="3.2.6"></a>
<a name="bp-vars-transient"></a>
#### 3.2.6 Transient Variables ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All variables that are not editable and have a initial value of zero or null should be marked as `Transient`.

Transient variables are variables that do not need to have their value saved and loaded and have an initial value of zero or null. This is useful for references to other objects and actors who's value isn't known until run-time.

This forces the variable to always initialize as zero or null, prevents the editor from ever saving a reference to it, and speeds up saving and loading of the blueprint class.

<a name="3.2.7"></a>
<a name="bp-vars-savegame"></a>
#### 3.2.7 SaveGame Variables ![#](https://img.shields.io/badge/lint-supported-green.svg)

Only use the SaveGame property of variables when inside a class derived from `SaveGame`. Use this property only if the `SaveGame` class should save this value.

Do **not** mix `SaveGame` and `Transient`, this does not make any sense.

<a name="3.2.8"></a>
<a name="bp-vars-config"></a>
#### 3.2.8 Config Variables ![#](https://img.shields.io/badge/lint-supported-green.svg)

Do not use the `Config Variable` flag. This makes it harder for designers to control blueprint behavior. Config variables should only be used in C++ for rarely changed variables. Think of them as `Advanced Advanced Display` variables.

## Contributors

* [Michael Allar](http://allarsblog.com): [GitHub](https://github.com/Allar), [Twitter](https://twitter.com/michaelallar)
* [CosmoMyzrailGorynych](https://github.com/CosmoMyzrailGorynych)
* [billymcguffin](https://github.com/billymcguffin)

## License

Copyright (c) 2016 Gamemakin LLC

See [LICENSE](/LICENSE)

**[⬆ Back to Top](#table-of-contents)**


## Amendments

We encourage you to fork this guide and change the rules to fit your team's style guide. Below, you may list some amendments to the style guide. This allows you to periodically update your style guide without having to deal with merge conflicts.

# };
