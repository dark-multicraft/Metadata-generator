# Minetest Metadata Generator (Fork)

This is a fork of [multi-nono/Metadata-generator](https://github.com/multi-nono/Metadata-generator).

This tool allows you to generate `/giveme` or `/give` commands with complex metadata for [MultiCraft](https://www.multicraft.world) right in your browser.

- **Japanese version**: `JA v2.html`
- **English version**: `EN v2.html`

## 日本語

### 概要
このツールは、Minetestのアイテムにメタデータ（説明文、色、エンチャント、ツール性能など）を追加するためのコマンドを簡単に生成するウェブアプリケーションです。インストールは不要で、`JA v2.html`をブラウザで開くだけで利用できます。

### 使い方（クイックスタート）
1.  `JA v2.html` ファイルをウェブブラウザで開きます。
2.  **アイテムの情報**で、ベースとなるアイテムID、数量、消耗度を入力します。
3.  **メタデータの変更**セクションの各ボタンを押し、開いた画面で詳細を設定します。
4.  **生成されたコマンド**エリアに表示されたコマンドをコピーし、Minetest内で使用します。

---

### 各機能の詳細解説

#### エンチャント (Enchantments)
アイテムに特殊能力を付与する機能です。Minetest本体にはエンチャントの仕組みのみが用意されており、具体的な効果はMODによって追加されます。そのため、サーバーや導入しているMODによって効果や種類が異なる場合があります。

- **使い方**:
  1. `[エンチャント]`ボタンを押します。
  2. 「タイプ」から能力を選択し、「レベル」で強度を指定して追加します。

- **代表的なエンチャントの例**:
  - `silk_touch` (シルクタッチ): 通常は別のアイテムに変わるブロック（例: 石炭鉱石→石炭）を、ブロックそのものの状態（石炭鉱石）でドロップさせます。ガラスなどを壊してもアイテムとして回収できるようになります。
  - `knockback` (ノックバック): 攻撃した相手をより遠くまで吹き飛ばします。

#### ツール性能 (Tool Capabilities)
ツールの物理的な基本性能（ステータス）を定義する、Minetestの標準機能です。`toolcaps`とも呼ばれます。MOD無しで動作し、ツールの挙動の根幹を担います。

- **設定項目（編集画面のタブ別）**:
  - `武器 (Weapon)`: 主に戦闘に関する性能です。
    - `ダメージ (Damage)`: `damage_groups`に相当し、`fleshy`（肉体系）などのグループに属するエンティティへの基本ダメージを設定します。
    - `攻撃間隔 (Attack Interval)`: `full_punch_interval`に相当し、最大ダメージを与えるために必要な攻撃ごとのクールダウン時間（秒）です。
  - `砕き (Cracky)` / `伐採 (Choppy)`など: ブロックに対する採掘性能です。
    - `グループ (Group)`: Minetestのブロックは`cracky`(石系)、`choppy`(木系)、`crumbly`(土系)などのグループに分類されます。この値が、ツールの性能とブロックの性質を関連付けます。
    - `時間 (Time)`: `times`に相当し、各グループの硬さレベル(1, 2, 3)ごとに、採掘にかかる時間を秒単位で設定します。
    - `最大レベル (Max Level)`: `maxlevel`に相当し、このツールで採掘可能なブロックの最大硬さレベルです。
    - `耐久消費 (Uses)`: 1回の使用で消費する耐久値です。
  - `ドロップLV (Drop LV)`: `max_drop_level`に相当します。設定したレベル以下のブロックからのみ、正規のドロップ品を得られるように制限する値です。例えば、MODで「ダイヤピッケルでないと黒曜石はドロップしない」という挙動を実装する際に使われます。

#### ツールランク (Tool Ranks)
人気のMOD **`toolranks`** によって追加される「ツールの成長」に関するメタデータです。ツールにレベルや経験値の概念を持たせ、使い込むことで性能が向上する仕組みを実装します。

- **設定項目**:
  - `Level (レベル)`: ツールの現在のランクです。`toolranks` MODでは、レベルが上がると主に耐久性が向上します（壊れにくくなる）。
  - `Uses (使用回数)`: ツールの現在の経験値です。この値が一定に達するとレベルアップします。
  - `Dug (掘削レベル)`: `toolranks`自体というより、他の様々なMODで利用されることがあるカスタム値です。「Dugレベル3のツールでないと掘れない」といった、ゲームの進行度（Tier）を管理するために使われることが多いです。

#### ツール性能表
ページ下部にあるこの表は、Minetestに標準で存在するツールの`ツール性能 (Tool Capabilities)`を一覧にした**参照専用のデータ集**です。

- **各列の意味**:
  - `ツール`: アイテム名です。
  - `グループ`: そのツールがどのブロックグループに対して特効を持つかを示します。
  - `時間 (lv1, lv2, lv3)`: 各硬さレベルのブロックを掘るのにかかる秒数です。
  - `最大レベル`: そのツールが掘れるブロックの最大硬さレベルです。
  - `耐久度 (uses)`: ツールが壊れるまでの総使用回数です。
  - `最大ドロップLV`: 正規のドロップ品を得られるブロックの最大レベルです。
  - `ダメージ`: `fleshy`グループに対する基本ダメージです。
  - `パンチ使用回数`: 1回の攻撃で消費する耐久値です。
  - `攻撃速度`: 攻撃のクールダウン時間（秒）です。
- **活用法**: この表で「鉄のつるはし」の性能を確認し、それを基準に「ツール性能編集画面」でオリジナルのカスタムツールを作成する、といった使い方ができます。MODで新しいツールを追加する際のバランス調整に不可欠です。

## English

### Overview
This tool is a web application that simplifies the process of generating Minetest commands for items with metadata (e.g., descriptions, colors, enchantments, tool capabilities). No installation is required; simply open `EN v2.html` in your browser.

### How to Use (Quick Start)
1.  Open the `EN v2.html` file in a web browser.
2.  In the **Item Information** section, enter the base item ID, quantity, and wear.
3.  Click the buttons in the **Modify Metadata** section to open editors and configure details.
4.  Copy the command from the **Generated Command** area and use it in Minetest.

---

### Detailed Feature Explanations

#### Enchantments
This feature adds special abilities to items. The Minetest engine provides the framework for enchantments, but the specific effects are defined by mods. Therefore, the types and effects of enchantments can vary depending on the server or installed mods.

- **How to use**:
  1. Click the `[Enchant]` button.
  2. Select an ability from the "Type" dropdown (e.g., `speed`, `damage`) and specify its strength in the "Level" field.

- **Examples of Common Enchantments**:
  - `silk_touch`: Allows you to collect blocks that would normally drop a different item (e.g., Coal Ore drops itself instead of a Lump of Coal). It also allows you to pick up fragile blocks like glass.
  - `knockback`: Knocks back the attacked entity further.

#### Tool Performance (Tool Capabilities)
This is a standard Minetest feature, also known as `toolcaps`, that defines a tool's fundamental physical properties (its "base stats"). It works without mods and is the core of a tool's behavior.

- **Parameters (Grouped by Editor Tabs)**:
  - `Weapon`: Primarily for combat.
    - `Damage`: Corresponds to `damage_groups` and sets the base damage dealt to entities in specific groups (e.g., `fleshy`).
    - `Attack Interval`: Corresponds to `full_punch_interval`, the cooldown time in seconds required between attacks to deal maximum damage.
  - `Cracky` / `Choppy`, etc.: Defines digging performance against block groups.
    - `Group`: Blocks in Minetest are categorized into groups like `cracky` (stone-like), `choppy` (wood-like), and `crumbly` (dirt-like). This links the tool's capabilities to the block's properties.
    - `Time`: Corresponds to `times`, setting the time in seconds to dig a block for each hardness level (1, 2, 3).
    - `Max Level`: Corresponds to `maxlevel`, the maximum hardness level this tool can dig.
    - `Uses`: The amount of wear consumed in a single use.
  - `Drop LV`: Corresponds to `max_drop_level`. This restricts the tool to only yield proper drops from blocks up to the specified level. It's used by mods to enforce progression (e.g., "Obsidian can only be dropped by a diamond pickaxe").

#### Tool Ranks
This metadata is not a standard feature but is for the popular **`toolranks`** mod, which adds a progression system to tools. It allows tools to have levels and experience points, improving as they are used.

- **Parameters**:
  - `Level`: The tool's current rank. In the `toolranks` mod, a higher level primarily increases the tool's durability (it breaks less quickly).
  - `Uses`: The tool's current experience points. The tool levels up when this value reaches a certain threshold.
  - `Dug`: A custom value often used by various progression mods. It defines a "digging tier," allowing mods to create blocks that can only be broken by a tool with a high enough `Dug` level.

#### Tool Performance Table
This table, located at the bottom of the page, is a **read-only reference dataset** that lists the `Tool Capabilities` of all standard tools in Minetest.

- **Column Meanings**:
  - `Tool`: The item name.
  - `Group`: The block group the tool is most effective against.
  - `Time (lv1, lv2, lv3)`: Time in seconds to dig blocks of the corresponding hardness level.
  - `Max Level`: The maximum hardness level the tool can dig.
  - `Durability (uses)`: The total number of uses before the tool breaks.
  - `Max Drop LV`: The maximum level of a block that will yield its proper drops.
  - `Damage`: Base damage against the `fleshy` group.
  - `Punch Uses`: Wear consumed per single attack.
  - `Attack Speed`: The attack cooldown in seconds.
- **How to Use It**: You can use this table to check the stats of an "Iron Pickaxe" and then use the "Tool Performance" editor to create a custom tool with your desired stats. It is an essential resource for balancing new tools in mods.
