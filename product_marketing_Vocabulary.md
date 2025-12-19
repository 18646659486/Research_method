## 产品营销本体词汇表（Ontology Vocabulary）

- 版本: 1.0
- 命名空间（base IRI）: `http://asiainfo.com/example-owl#`
- 本体名称: `ex:Product_marketing`（产品营销）
- 创建日期: 2025-12-19
- 简述: 定义产品营销领域的核心类、对象属性、数据属性与可调用逻辑/行动，用于描述产品目录、产品策略、营销活动、渠道、接触记录、用户画像与行为特征等要素及其关系，支撑“用户到产品”“产品到人”“营销方案预测”等业务场景。

### 前缀（Prefixes）

- `rdf`: `http://www.w3.org/1999/02/22-rdf-syntax-ns#`
- `rdfs`: `http://www.w3.org/2000/01/rdf-schema#`
- `owl`: `http://www.w3.org/2002/07/owl#`
- `xsd`: `http://www.w3.org/2001/XMLSchema#`
- `prov`: `http://www.w3.org/ns/prov#`
- `dcterms`: `http://purl.org/dc/terms/`
- `ex`: `http://asiainfo.com/example-owl#`

---

## 目录
- [产品营销本体词汇表（Ontology Vocabulary）](#产品营销本体词汇表ontology-vocabulary)
  - [前缀（Prefixes）](#前缀prefixes)
- [目录](#目录)
- [概览与适用范围](#概览与适用范围)
- [IRI 后缀（Local Names）](#iri-后缀local-names)
- [类（Classes）](#类classes)
  - [核心与抽象](#核心与抽象)
  - [领域对象](#领域对象)
    - [营销活动与内容](#营销活动与内容)
    - [产品与策略](#产品与策略)
    - [用户与画像/行为](#用户与画像行为)
  - [本体名称](#本体名称)
  - [行动与逻辑](#行动与逻辑)
    - [行动（Actions）](#行动actions)
    - [逻辑函数（Logics）](#逻辑函数logics)
- [对象属性（Object Properties）](#对象属性object-properties)
  - [绑定属性：`bindAction`/`bindLogic`/`hasParameter`](#绑定属性bindactionbindlogichasparameter)
  - [关系分组：拥有/属于/关联/引用](#关系分组拥有属于关联引用)
  - [详细对象属性表](#详细对象属性表)
- [数据属性（Datatype Properties）](#数据属性datatype-properties)
  - [标识与时间分区](#标识与时间分区)
  - [活动与营销效果指标](#活动与营销效果指标)
  - [渠道与营销内容配置](#渠道与营销内容配置)
  - [产品与权益属性](#产品与权益属性)
  - [用户画像/行为与客群标签](#用户画像行为与客群标签)
  - [按类拆分（Domain→Properties）](#按类拆分domainproperties)
- [命名个体与枚举（Named Individuals & Enums）](#命名个体与枚举named-individuals--enums)
- [建模约束与规则（Axioms）](#建模约束与规则axioms)
- [示例绑定（Examples）](#示例绑定examples)
- [修订记录](#修订记录)

---

## 概览与适用范围
- 目标: 构建面向“产品营销”的统一语义模型，覆盖产品目录与策略、营销活动与渠道、接触记录与历史效果、用户基础信息与画像行为等对象，以及相关指标与函数/行动。
- 适用场景:
  - 用户到产品：根据用户画像和行为进行产品推荐；
  - 产品到人：根据产品策略筛选目标用户并创建营销活动；
  - 方案转化率预测：基于历史营销数据与当前活动配置评估转化率；
  - 渠道智能决策与触达执行：选择渠道并批量推送触达，并记录接触历史。
- 对齐标准: 抽象类 `ex:Entity` 与 `ex:Action` / `ex:Logic` 与 PROV-O 中的 `prov:Entity` / `prov:Activity` 对齐。

---

## IRI 后缀（Local Names）
以下列出本体命名空间 `http://asiainfo.com/example-owl#` 之后的常用本地名（local names）。

- 命名空间前缀：`ex:` → `http://asiainfo.com/example-owl#`

### 类（Classes）后缀
- 抽象与核心：`Entity`、`Object`、`Action`、`Logic`、`Parameter`、`ListType`、`DictType`、`ontologyName`
- 领域对象：
  - 营销：`Campaign`、`MarketingContent`、`HistoricalMarketingData`、`ChannelInfo`、`ContactRecord`、`ProductStrategy`
  - 产品：`ProductCatalog`
  - 用户：`UserInfo`、`UserProfile`、`UserBehavior`

### 对象属性（Object Properties）后缀
- 绑定与参数：`bindAction`、`bindLogic`、`hasParameter`、`paramTypeNode`、`hasMiddleObject`
- 关系设计辅助：`domainAttribute`、`rangeAttribute`、`custom_relation`

### 数据属性（Datatype Properties）后缀（部分示例）
- 标识与时间：`ID`、`自增主键`、`活动ID`、`活动名称`、`渠道ID`、`用户ID`、`产品ID`、`日期`、`分区字段`、`开始时间`、`结束时间`、`更新时间`、`联系时间`、`成功时间`、`生效开始时间`、`生效结束时间` 等
- 活动与效果：`预算金额`、`目标用户数`、`触达用户数`、`实际触达数`、`实际转化数`、`预测转化率`、`预测准确率`、`当前转化率`、`总成本`、`总收入`、`投资回报率` 等
- 渠道与内容：`渠道名`、`渠道名称`、`渠道类型`、`渠道描述`、`渠道统计`、`近3日统计`、`状态`、`审批状态`、`审批时间`、`审批人`、`标题`、`副标题`、`正文`、`按钮文字`、`按钮链接`、`关闭文字`、`展示数`、`点击数`、`点击率`、`优先级`、`模板变量`、`适用人群`、`适用产品` 等
- 产品与权益：`产品名称`、`产品类型`、`产品品牌`、`产品本地流量`、`产品专用流量`、`产品国际语音`、`产品原价`、`产品现价`、`产品优惠价`、`产品原始价格`、`产品办理价格`、`产品优惠价格`、`产品合约期`、`有效期`、`可叠加`、`可兑换`、`奖励名称`、`赠送金额`、`赠送话费金额`、`赠送话费时间`、`区域限制` 以及各类会员/应用权益字段（如 `音乐应用`、`视频应用`、`阅读应用`、`网盘应用`、`体育应用`、`会员等级`、`试用会员` 等）
- 用户画像/行为与客群标签：`电话号码`、`年龄`、`性别`、`是否实名`、`是否校园用户`、`是否5G资费用户`、`是否是5G终端`、`是否是不限流量套餐用户`、`是否为泛体育偏好用户`、`是否有宠物`、`是否是租户`、`是否副卡`、`是否智能机`、`是否存量用户` 等，以及大量用 0/1 标识的客群标签属性，如 `商务出行客群`、`旅游发烧客群旅居候鸟`、`追星音乐客群`、`网约车司机用户`、`居家办公`、`外卖` 等。

---

## 类（Classes）

### 核心与抽象
- `ex:Entity`
  - 抽象实体基类，对齐 `prov:Entity`，所有本体对象类的共同超类。
- `ex:Object`
  - 业务对象抽象基类，所有具体领域对象（如活动、产品、用户）均继承自该类。
- `ex:Action`
  - 行动类，对齐 `prov:Activity`，表示可触发的业务动作（如“执行触达动作”“回填渠道历史信息”等）。
- `ex:Logic`
  - 决策/逻辑函数类，对齐 `prov:Activity`，表示可调用算法/策略函数，用于推荐、匹配和评估。
- `ex:Parameter`
  - 函数参数类，用于描述逻辑函数/行动的输入参数结构（名称、类型、是否可选、复杂类型节点等）。
- `ex:ListType` / `ex:DictType`
  - 复杂参数类型描述类，分别表示列表类型和字典类型的结构描述。
- `ex:ontologyName`
  - 本体名称类，用于声明本体名称与元信息。

### 领域对象

#### 营销活动与内容
- `ex:Campaign`
  - 营销活动对象，记录活动的基本属性、预算、目标人群、促销方案与执行状态。
  - 主键：`ex:活动ID`；标题：`ex:活动名称`。
- `ex:MarketingContent`
  - 营销文案对象，描述不同渠道的文案模板与内容（标题、副标题、正文、按钮文字、模板变量等）。
  - 主键：`ex:ID`。
- `ex:HistoricalMarketingData`
  - 历史营销记录对象，保存活动执行历史与转化结果（目标用户数、实际触达数、实际转化数、转化率、成本/收入等）。
  - 主键：`ex:ID`。
- `ex:ChannelInfo`
  - 渠道配置对象，用于描述营销渠道（如短信、APP、10086 弹窗、外呼）的静态属性与规则（是否推送、是否可办理、是否重复、重复间隔等）。
  - 主键：`ex:渠道ID`；标题：`ex:渠道名`。
- `ex:ContactRecord`
  - 渠道接触记录对象，记录单次用户接触行为（触达/接收/接通/办理标识、推荐原因、执行活动 ID、通话时长、联系结果等）。
  - 主键：`ex:ID`。

#### 产品与策略
- `ex:ProductCatalog`
  - 产品目录对象，描述产品的基础信息与资源配置（产品类型、品牌、本地/全国流量、语音资源、权益应用、原价/现价/优惠价等）。
  - 主键：`ex:ID`（自增主键）；同时使用 `ex:产品ID`、`ex:产品名称` 等业务键。
- `ex:ProductStrategy`
  - 产品策略/画像对象，从营销视角描述产品的定价策略、促销方案、权益组合与业务线条（如产品合约期、优惠价格、赠送话费等）。
  - 主键：`ex:自增主键`。

#### 用户与画像/行为
- `ex:UserInfo`
  - 用户基本信息对象，包含电话号码、年龄、实名状态、终端/资费属性、是否校园/融合/日租卡用户等基础标签。
  - 主键：`ex:自增主键`；关键业务属性包括 `ex:用户ID`、`ex:电话号码` 等。
- `ex:UserProfile`
  - 用户画像对象，聚合用户价值、网络体验、产品使用特征与客群标签（如是否5G基站覆盖用户、是否不限流量套餐用户、是否符合终端合约办理资格等）。
  - 主键：`ex:自增主键`。
- `ex:UserBehavior`
  - 用户行为对象，记录用户在渠道/产品上的行为数据，如浏览/点击记录、近7天内营销过的产品及结果、行为偏好等。
  - 主键：`ex:自增主键`。

### 本体名称
- `ex:Product_marketing a ex:ontologyName`
  - 使用 `rdfs:label "产品营销"@zh` 声明本体名称，用于标识该领域模型。

### 行动与逻辑

#### 行动（Actions）
- `ex:ExecuteTouchAction`
  - 作用：执行触达动作，批量向目标用户通过指定渠道发送营销触达（如 10086 弹窗）。
  - 绑定对象：`ex:Campaign ex:bindAction ex:ExecuteTouchAction`。
  - 典型参数（通过 `ex:hasParameter` 声明）：
    - `campaign_id` (`xsd:string`，必填)：活动 ID；
    - `product_id` (`xsd:string`，必填)：产品 ID；
    - `channel_id` (`xsd:string`，必填)：渠道 ID；
    - `target_users`（列表类型，必填）：目标用户列表（`ex:ListType`）；
    - `content_id` (`xsd:string`，可选)：营销文案 ID；
    - `message_template`（字典类型，可选，`ex:DictType`）：文案模板变量。
- `ex:RecordContactHistory`
  - 作用：批量记录接触历史，将触达结果写入 `ex:ContactRecord` 对象。
  - 绑定对象：`ex:ContactRecord ex:bindAction ex:RecordContactHistory`。
  - 典型参数：`campaign_id`、`product_id`、`channel_id`、`target_users` 等。
- `ex:UpdateConversionStatus`
  - 作用：更新转化状态，将接触记录与实际办理结果关联，用于闭环营销效果。
  - 绑定对象：`ex:ContactRecord ex:bindAction ex:UpdateConversionStatus`。

#### 逻辑函数（Logics）
- `ex:evaluate_campaign`
  - 作用：营销方案评估函数，用于预测营销方案转化率，输出预测结果与风险分析/建议。
  - 典型输入参数：
    - `product_id` (`xsd:string`，必填)、`channel_id` (`xsd:string`，必填)；
    - `discount_rate` (`xsd:double`，可选，默认 0.0)；
    - `holiday_season` (`xsd:string`，可选)；
    - `content_id` (`xsd:string`，可选)。
  - 绑定对象（部分示例）：`ex:ContactRecord`、`ex:HistoricalMarketingData`、`ex:ProductCatalog` 等通过 `ex:bindLogic` 与之关联。
- `ex:match_product_to_users`
  - 作用：产品到人匹配函数，根据产品特征和用户画像，筛选目标用户并创建营销活动。
  - 典型输入参数：
    - `product_id`、`channel_id`（必填）；
    - `campaign_name`、`video_prefer_min`、`game_prefer_min`、`arpu_min`、`flow_saturation_max`、`top_n` 等可选控制参数。
  - 输出：返回 `campaign_id`、`total_matched`、`ranked_users` 等结果。
  - 绑定对象：`ex:ProductCatalog`、`ex:ChannelInfo`、`ex:UserInfo`、`ex:UserProfile`、`ex:ContactRecord`、`ex:ProductStrategy` 等。
- `ex:recommend_products`
  - 作用：用户到产品推荐函数，根据用户画像与历史行为，为用户推荐最合适的产品及渠道。
  - 典型输入参数：
    - `user_id`（必填）、`channel_id`（可选）、`top_n`（默认 3）、`product_weight`（默认 0.7）、`channel_weight`（默认 0.3）。
  - 输出：`selected_channel`、`user_insights`、`recommended_products`、`details` 等。
  - 绑定对象：`ex:UserProfile`、`ex:UserInfo`、`ex:ProductCatalog`、`ex:ProductStrategy` 等。

---

## 对象属性（Object Properties）

### 绑定属性：`bindAction`/`bindLogic`/`hasParameter`
- `ex:bindAction`
  - 用途：在对象类与 `ex:Action` 行动之间建立绑定关系，指明某对象可执行哪些行动。
  - 典型用法：`ex:Campaign ex:bindAction ex:ExecuteTouchAction`、`ex:ContactRecord ex:bindAction ex:RecordContactHistory` 等。
- `ex:bindLogic`
  - 用途：在对象类与 `ex:Logic` 逻辑函数之间建立绑定关系，指明可以在哪些对象视图上调用相关算法。
  - 典型用法：`ex:UserProfile ex:bindLogic ex:recommend_products`、`ex:ProductCatalog ex:bindLogic ex:match_product_to_users` 等。
- `ex:hasParameter`
  - 用途：用于逻辑/行动与其参数（`ex:Parameter`）之间的关系，声明参数列表。
- `ex:paramTypeNode`
  - 用途：当参数类型为列表或字典时，指向具体类型节点（`ex:ListType` / `ex:DictType`）。
- `ex:hasMiddleObject`
  - 用途：描述多对多关系时，中间对象的指示属性（在该本体中可用于扩展复杂关系设计）。
- `ex:custom_relation`
  - 用途：预留的通用对象关系属性，用于自定义对象与对象之间的业务关系。
- `ex:domainAttribute` / `ex:rangeAttribute`
  - 用途：作为注解属性，说明对象属性在域和值域端使用哪个数据属性作为关联键（如使用 `ex:活动ID`、`ex:产品ID`、`ex:用户ID` 等进行关联）。

### 关系分组：拥有/属于/关联/引用
- 营销活动关系：
  - Campaign 与 ProductCatalog/MarketingContent/ChannelInfo/ContactRecord 之间可通过共享键（`活动ID`、`产品ID`、`渠道ID`、`用户ID` 等）以及 `ex:custom_relation` 建模“活动使用的产品/渠道/文案”“活动产生的接触记录”等关系。
- 产品与用户/画像关系：
  - ProductCatalog / ProductStrategy 通过产品维度数据属性与用户画像/行为对象相联，用于刻画“适用人群”“目标客群特征”等关联。
- 渠道与接触记录关系：
  - ChannelInfo 与 ContactRecord 通过 `渠道ID`、`渠道类型` 等关联，用于统计渠道表现与触达记录。

（`product_marketing.owl` 中主要使用数据层面的共享键以及逻辑/行动绑定来组织对象间的关联，对象属性本身较为精简。）

### 详细对象属性表

下表列出产品营销本体中主要的业务关系对象属性，按 Domain/Range、逆属性与键注解进行整理（风格与 CEM 本体保持一致）：

| 属性 | 标签 | Domain | Range | 逆属性 | 子属性于 | 键注解（Domain/Range） | 说明 |
|---|---|---|---|---|---|---|---|
| `ex:bindAction` | 绑定行动 | `ex:Object` | `ex:Action` | - | - | - | 对象可执行的行动绑定 |
| `ex:bindLogic` | 绑定逻辑 | `ex:Object` | `ex:Logic` | - | - | - | 对象可调用的逻辑函数绑定 |
| `ex:hasParameter` | 拥有参数 | `ex:Logic`/`ex:Action` | `ex:Parameter` | - | - | - | 逻辑/行动的形参声明 |
| `ex:BUSINESSOBJECTATTRIBUTEVALUE__INJECTIONLABEL` | 引用 | `ex:UserBehavior` | `ex:ContactRecord` | `ex:isReferencedBy` | `ex:custom_relation` | `ex:用户ID` / `ex:用户ID` | 用户行为引用接触记录 |
| `ex:isReferencedBy` | 被引用 | `ex:ContactRecord` | `ex:UserBehavior` | `ex:BUSINESSOBJECTATTRIBUTEVALUE__INJECTIONLABEL` | `ex:custom_relation` | 同上 | 接触记录被用户行为引用 |
| `ex:BUSINESSOBJECTATTRIBUTEVALUE__INJECTIONLABEL` | 引用 | `ex:ContactRecord` | `ex:ChannelInfo` | `ex:isReferencedBy` | `ex:custom_relation` | `ex:ID` / `ex:渠道ID` | 接触记录引用渠道配置 |
| `ex:isReferencedBy` | 被引用 | `ex:ChannelInfo` | `ex:ContactRecord` | `ex:BUSINESSOBJECTATTRIBUTEVALUE__INJECTIONLABEL` | `ex:custom_relation` | `ex:渠道ID` / `ex:ID` | 渠道被接触记录引用 |
| `ex:belonged_to` | 被属于 | `ex:MarketingContent` | `ex:Campaign` | `ex:TransmissionResourceData_belongsTo` | `ex:custom_relation` | `ex:文案ID` / `ex:内容ID` | 文案属于活动 |
| `ex:TransmissionResourceData_belongsTo` | 属于 | `ex:Campaign` | `ex:MarketingContent` | `ex:belonged_to` | `ex:custom_relation` | `ex:内容ID` / `ex:文案ID` | 活动关联的营销文案 |
| `ex:was_owned` | 被拥有 | `ex:ProductStrategy` | `ex:ProductCatalog` | `ex:has` | `ex:custom_relation` | `ex:产品ID` / `ex:产品ID` | 产品策略被产品目录拥有 |
| `ex:has` | 拥有 | `ex:ProductCatalog` | `ex:ProductStrategy` | `ex:was_owned` | `ex:custom_relation` | 同上 | 产品目录拥有产品策略 |
| `ex:was_owned` | 被拥有 | `ex:UserProfile` | `ex:UserInfo` | `ex:has` | `ex:custom_relation` | `ex:用户ID` / `ex:用户ID` | 用户画像被用户基础信息拥有 |
| `ex:has` | 拥有 | `ex:UserInfo` | `ex:UserProfile` | `ex:was_owned` | `ex:custom_relation` | 同上 | 用户拥有画像对象 |
| `ex:has` | 拥有 | `ex:ProductCatalog` | `ex:Campaign` | `ex:was_owned` | `ex:custom_relation` | `ex:产品ID` / `ex:计划ID` | 产品目录拥有活动（通过计划ID） |
| `ex:was_owned` | 被拥有 | `ex:Campaign` | `ex:ProductCatalog` | `ex:has` | `ex:custom_relation` | `ex:计划ID` / `ex:产品ID` | 活动被产品目录拥有 |
| `ex:isPartOf` | 属于 | `ex:UserProfile` | `ex:UserBehavior` | `ex:belonged_to` | `ex:custom_relation` | `ex:用户ID` / `ex:用户ID` | 用户画像属于用户行为视图 |
| `ex:belonged_to` | 被属于 | `ex:UserBehavior` | `ex:UserProfile` | `ex:isPartOf` | `ex:custom_relation` | 同上 | 用户行为被用户画像视图关联 |
| `ex:has` | 拥有 | `ex:UserInfo` | `ex:UserBehavior` | `ex:was_owned` | `ex:custom_relation` | `ex:用户ID` / `ex:用户ID` | 用户拥有行为对象 |
| `ex:was_owned` | 被拥有 | `ex:UserBehavior` | `ex:UserInfo` | `ex:has` | `ex:custom_relation` | 同上 | 用户行为被用户基础信息拥有 |
| `ex:belonged_to` | 被属于 | `ex:HistoricalMarketingData` | `ex:Campaign` | `ex:ComprehensiveManagementData_belongsTo` | `ex:custom_relation` | `ex:活动ID` / `ex:活动ID` | 历史营销数据属于活动 |
| `ex:ComprehensiveManagementData_belongsTo` | 属于 | `ex:Campaign` | `ex:HistoricalMarketingData` | `ex:belonged_to` | `ex:custom_relation` | 同上 | 活动关联的历史营销记录 |
| `ex:is_linked_to` | 被关联 | `ex:ContactRecord` | `ex:ProductCatalog` | `ex:linkedWith` | `ex:custom_relation` | `ex:产品ID` / `ex:产品ID` | 接触记录被产品目录关联 |
| `ex:linkedWith` | 关联 | `ex:ProductCatalog` | `ex:ContactRecord` | `ex:is_linked_to` | `ex:custom_relation` | 同上 | 产品目录与接触记录的关联 |
| `ex:has` | 拥有 | `ex:ContactRecord` | `ex:Campaign` | `ex:was_owned` | `ex:custom_relation` | `ex:活动ID` / `ex:活动ID` | 接触记录拥有活动标识 |
| `ex:was_owned` | 被拥有 | `ex:Campaign` | `ex:ContactRecord` | `ex:has` | `ex:custom_relation` | 同上 | 活动被接触记录引用 |

> 说明：上表仅覆盖 `product_marketing.owl` 中显式定义的主要业务关系对象属性；若后续扩展新的子属性，可按同样格式补充到表格中。

---

## 数据属性（Datatype Properties）

### 标识与时间分区

| 分组 | 典型属性 | 说明 |
|---|---|---|
| 标识属性 | `ex:ID`、`ex:自增主键`、`ex:活动ID`、`ex:产品ID`、`ex:渠道ID`、`ex:用户ID` | 统一的主键与业务键，用于唯一标识对象并在不同对象间建立键关联（如 Campaign/ProductCatalog/ContactRecord 等）。 |
| 分区与时间 | `ex:日期`、`ex:分区字段`、`ex:开始时间`、`ex:结束时间`、`ex:生效开始时间`、`ex:生效结束时间`、`ex:联系时间`、`ex:策略时间`、`ex:成功时间`、`ex:更新时间` | 分区和时间类字段，用于活动生命周期、文案生效区间、接触记录时间戳及多对象的更新时间管理。 |

### 活动与营销效果指标

| 分组 | 典型属性 | 说明 |
|---|---|---|
| 活动配置 | `ex:活动名称`、`ex:活动类型`、`ex:活动来源`、`ex:计划ID`、`ex:计划名称`、`ex:AI推荐`、`ex:促销类型`、`ex:促销率`、`ex:原价`、`ex:促销价`、`ex:预算金额` | 描述活动的名称、类型、来源、是否为智能推荐、促销方式与力度，以及预算和定价信息。 |
| 目标与实际效果 | `ex:目标用户数`、`ex:触达用户数`、`ex:实际触达数`、`ex:实际转化数`、`ex:预测转化率`、`ex:当前转化率`、`ex:预测准确率`、`ex:总成本`、`ex:总收入`、`ex:投资回报率` | 记录活动目标与执行结果，包括触达/转化数量、预测与实时转化率、准确率以及成本、收入和 ROI 指标。 |
| 状态与审批 | `ex:活动状态`、`ex:审批状态`、`ex:审批时间`、`ex:审批人` | 活动和文案的状态与审批流程字段，用于追踪生命周期与审核进度。 |

### 渠道与营销内容配置

| 分组 | 典型属性 | 说明 |
|---|---|---|
| 渠道属性（`ex:ChannelInfo`） | `ex:渠道ID`、`ex:渠道名`、`ex:渠道名称`、`ex:渠道类型`、`ex:渠道描述` | 渠道的基础标识与名称、类型和描述信息。 |
| 渠道规则 | `ex:是否有效`、`ex:是否推送`、`ex:是否有序`、`ex:是否重复`、`ex:是否手动`、`ex:重复间隔` | 渠道可用性、是否推送/可办理、是否允许重复及重复间隔等业务规则。 |
| 渠道统计 | `ex:渠道统计`、`ex:近3日统计` | 以 JSON 形式存放的渠道触达统计与近阶段统计信息。 |
| 文案内容结构（`ex:MarketingContent`） | `ex:标题`、`ex:副标题`、`ex:正文`、`ex:关闭文字`、`ex:按钮文字`、`ex:按钮链接` | 文案的标题、副标题、正文以及按钮相关文案和链接。 |
| 文案模板与适用范围 | `ex:模板变量`、`ex:适用人群`、`ex:适用产品`、`ex:渠道类型` | 文案模板变量定义及其适用的人群、产品和渠道范围。 |
| 文案绩效与生命周期 | `ex:展示数`、`ex:点击数`、`ex:点击率`、`ex:状态`、`ex:优先级`、`ex:生效开始时间`、`ex:生效结束时间`、`ex:审批状态`、`ex:审批时间`、`ex:审批人` | 文案的效果指标、优先级、状态以及生效区间与审批信息。 |
| 接触记录识别与联系信息（`ex:ContactRecord`） | `ex:ID`、`ex:活动ID`、`ex:渠道ID`、`ex:用户ID`、`ex:执行活动ID`、`ex:序列号`、`ex:联系时间`、`ex:通话时长`、`ex:呼叫人员`、`ex:职位`、`ex:推荐原因` | 接触记录的标识、关联键及通话/联系相关信息。 |
| 接触结果标记 | `ex:是否尝试推荐`、`ex:联系成功`、`ex:是否订单`、`ex:是否接收`、`ex:是否智能推荐策划`、`ex:是否成功` | 接触是否发生、是否成功接触/办理等 0/1 标志，用于效果归因。 |

### 产品与权益属性

| 分组 | 典型属性 | 说明 |
|---|---|---|
| 基础标识与描述 | `ex:产品ID`、`ex:产品名称`、`ex:产品类型`、`ex:产品品牌`、`ex:产品描述`、`ex:本地地址` | 产品的基本标识、名称、类型和品牌信息，以及所在本地/区域描述。 |
| 价格与合约 | `ex:产品原价`、`ex:产品现价`、`ex:产品优惠价`、`ex:产品原始价格`、`ex:产品办理价格`、`ex:产品优惠价格`、`ex:产品合约期`、`ex:有效期` | 产品定价与促销相关字段，以及合约期和生效期信息。 |
| 流量与语音资源 | `ex:产品本地流量`、`ex:产品专用流量`、`ex:产品包含的宽带带宽`、`ex:产品国际语音` | 产品包含的本地/专属流量、宽带带宽和国际语音资源配置。 |
| 权益与会员 | `ex:奖励名称`、`ex:赠送金额`、`ex:赠送话费金额`、`ex:赠送话费时间`、`ex:试用会员`、`ex:体验权益类型`、`ex:权益体验时间`、`ex:音乐应用`、`ex:视频应用`、`ex:阅读应用`、`ex:网盘应用`、`ex:体育应用`、`ex:会员等级` | 各类权益、赠送资源和会员应用相关字段，描述产品附带的权益组合。 |
| 资格与客群 | `ex:可叠加`、`ex:可兑换`、`ex:区域限制`、`ex:老人专属`、`ex:学生专属` | 产品在叠加、兑换和适用客群（老人、学生等）方面的资格限制。 |

### 用户画像/行为与客群标签

| 分组 | 典型属性 | 说明 |
|---|---|---|
| 用户基础信息（`ex:UserInfo`） | `ex:用户ID`、`ex:电话号码`、`ex:年龄` | 用户的基础标识和年龄等基础属性。 |
| 终端/资费类（`ex:UserInfo`） | `ex:是否5G资费用户`、`ex:是否是5G终端`、`ex:是否智能机`、`ex:是否校园用户`、`ex:是否副卡`、`ex:是否存量用户` | 终端能力和资费类型相关的标志位，用于刻画用户的网络与资费特征。 |
| 社会角色与生活方式（`ex:UserInfo`） | `ex:商务出行客群`、`ex:旅游发烧客群旅居候鸟`、`ex:网约车司机用户`、`ex:主播`、`ex:居家办公`、`ex:快递物流`、`ex:外卖`、`ex:是否有宠物` | 通过 0/1 标签描述用户的生活/出行/职业场景和兴趣偏好。 |
| 用户画像价值与资格（`ex:UserProfile`） | `ex:手机账户余额`、`ex:是否符合终端合约办理资格`、`ex:是否是不限流量套餐用户` | 反映用户价值和办理终端合约/不限流量等资格的画像字段。 |
| 用户画像使用环境（`ex:UserProfile`） | `ex:是否是5G基站覆盖用户` | 描述用户网络覆盖环境的画像字段。 |
| 终端/APP 使用（`ex:UserProfile`） | `ex:手机是否安装运营商官方一级APP` | 终端是否安装运营商官方 APP 的标志，用于判断触达能力。 |
| 用户行为（`ex:UserBehavior`） | 近 7 天营销产品及结果字段、渠道行为统计字段（文本/JSON） | 记录近期营销接触的产品及结果，以及按渠道统计的行为数据，是推荐与匹配逻辑的重要输入。 |

### 按类拆分（Domain→Properties）
以下以“Domain 类 → 关键数据属性分组”的形式，总结主要对象的字段（详细枚举仍以 `product_marketing.owl` 为准）：

| Domain 类 | 主键/标识 | 关键属性分组 | 说明 |
|---|---|---|---|
| `ex:Campaign` | `ex:活动ID`、`ex:计划ID`、`ex:计划名称`、`ex:内容ID` | 活动说明类：`ex:活动名称`、`ex:活动类型`、`ex:活动来源`、`ex:活动描述`；价格与促销：`ex:原价`、`ex:促销价`、`ex:促销率`、`ex:促销类型`、`ex:AI推荐`；目标与执行：`ex:目标受众规则`、`ex:目标用户数`、`ex:触达用户数`、`ex:活动状态`；时间与预算：`ex:开始时间`、`ex:结束时间`、`ex:预算金额`、`ex:预测转化率`、`ex:当前转化率` | 用于描述和管理营销活动的完整生命周期与效果指标。 |
| `ex:HistoricalMarketingData` | `ex:ID`、`ex:活动ID`、`ex:产品ID`、`ex:渠道ID` | 目标与结果：`ex:目标用户数`、`ex:实际触达数`、`ex:实际转化数`；效果指标：`ex:预测转化率`、`ex:预测准确率`、`ex:总成本`、`ex:总收入`、`ex:投资回报率`；画像摘要：`ex:目标受众特征`（JSON） | 存放活动执行历史、实际结果与效果评估，用于训练与评估算法。 |
| `ex:ChannelInfo` | `ex:渠道ID`、`ex:渠道名` | 类型与规则：`ex:渠道类型`、`ex:渠道描述`、`ex:是否有效`、`ex:是否推送`、`ex:是否有序`、`ex:是否重复`、`ex:是否手动`、`ex:重复间隔`；统计信息：`ex:渠道统计`、`ex:近3日统计` | 描述渠道的静态配置与规则，以及触达统计信息。 |
| `ex:MarketingContent` | `ex:ID` | 内容配置：`ex:标题`、`ex:副标题`、`ex:正文`、`ex:按钮文字`、`ex:按钮链接`、`ex:关闭文字`、`ex:模板变量`；适用规则：`ex:适用人群`、`ex:适用产品`、`ex:渠道类型`；生命周期与效果：`ex:状态`、`ex:审批状态`、`ex:审批时间`、`ex:审批人`、`ex:生效开始时间`、`ex:生效结束时间`、`ex:展示数`、`ex:点击数`、`ex:点击率`、`ex:优先级` | 用于管理多渠道营销文案模板及其审批、上线和效果表现。 |
| `ex:ContactRecord` | `ex:ID`、`ex:活动ID`、`ex:产品ID`、`ex:渠道ID`、`ex:用户ID`、`ex:执行活动ID`、`ex:序列号` | 时间与人员：`ex:联系时间`、`ex:策略时间`、`ex:成功时间`、`ex:呼叫人员`、`ex:市场人员`、`ex:职位`；结果与标签：`ex:通话时长`、`ex:推荐原因`、`ex:是否尝试推荐`、`ex:联系成功`、`ex:是否订单`、`ex:是否接收`、`ex:是否智能推荐策划`、`ex:是否成功` | 记录单次接触行为的全过程，用于转化归因与链路分析。 |
| `ex:ProductCatalog` | `ex:ID`、`ex:产品ID`、`ex:产品名称` | 价格与合约：`ex:产品原价`、`ex:产品现价`、`ex:产品优惠价`、`ex:有效期`、`ex:激活规则`；资源配置：`ex:产品本地流量`、`ex:产品专用流量`、`ex:产品包含的宽带带宽`、`ex:产品国际语音`；权益与限制：`ex:奖励名称`、`ex:赠送金额`、`ex:赠送话费时间`、`ex:可叠加`、`ex:可兑换`、`ex:区域限制`、`ex:老人专属`、`ex:学生专属`；会员应用：`ex:音乐应用`、`ex:视频应用`、`ex:阅读应用`、`ex:网盘应用`、`ex:体育应用`、`ex:会员等级`、`ex:试用会员`；其他：`ex:产品描述`、`ex:本地地址`、`ex:产品标签` | 从产品角度描述定价、资源、权益和适用客群，是推荐/匹配的核心对象。 |
| `ex:ProductStrategy` | `ex:自增主键`、`ex:产品ID`、`ex:产品名称` | 策略与定价：`ex:产品业务线条`、`ex:产品合约期`、`ex:产品原始价格`、`ex:产品办理价格`、`ex:产品优惠价格`；权益策略：`ex:赠送话费金额`、`ex:赠送话费时间`、`ex:体验权益类型`、`ex:权益体验时间`、`ex:是否可在积分商城中兑换` | 从策略视角补充产品的业务线条、价格策略与积分兑换等信息。 |
| `ex:UserInfo` / `ex:UserProfile` / `ex:UserBehavior` | `ex:自增主键`、`ex:用户ID` | 用户基础信息、画像与行为标签：包括资费、终端、场景、兴趣与人群属性，以及近期营销产品及结果、渠道行为统计等 | 共同构成用于产品推荐和人群筛选的用户视图与行为特征。 |

---

## 命名个体与枚举（Named Individuals & Enums）
- 当前 `product_marketing.owl` 中主要通过数据属性值与业务字典（如渠道类型、活动状态等）表达枚举含义，而未显式建模为命名个体。
- 渠道类型示例：`SMS`、`APP`、`10086_POPUP`、`OUTBOUND` 等（通过 `ex:渠道类型` 表达）。
- 活动/文案状态示例：`CREATED`、`RUNNING`、`PAUSED`、`COMPLETED`、`CANCELLED`、`DRAFT`、`ACTIVE`、`INACTIVE`、`ARCHIVED` 等（通过 `ex:活动状态`、`ex:状态` 表达）。

---

## 建模约束与规则（Axioms）
- 继承与对齐：
  - `ex:Entity ⊑ prov:Entity`，`ex:Action ⊑ prov:Activity`，`ex:Logic ⊑ prov:Activity`；
  - 所有领域对象（Campaign、ProductCatalog、UserInfo 等）均继承自 `ex:Object`。
- 键注解：
  - 对象类通过 `ex:hasPrimaryKey` 指定主键数据属性（如 Campaign→`ex:活动ID`，ChannelInfo→`ex:渠道ID`，UserInfo→`ex:自增主键` 等）；
  - 可通过 `ex:hasTitle` 指定显示标题属性（如 Campaign→`ex:活动名称`，ChannelInfo→`ex:渠道名` 等）。
- 关系键匹配：
  - 对象间关系通过共享的业务键（如 `活动ID`、`渠道ID`、`产品ID`、`用户ID`）和注解属性 `ex:domainAttribute` / `ex:rangeAttribute` 进行约束；
  - 允许通过中间对象（如扩展的桥接类）配合 `ex:hasMiddleObject` 描述多对多关系。
- 逻辑/行动参数：
  - 所有逻辑函数和行动通过 `ex:hasParameter` 声明参数列表，配合 `ex:paramName`、`ex:paramType`、`ex:isOptional`、`ex:paramTypeNode` 等，实现参数元数据建模。

---

## 示例绑定（Examples）
- 对象绑定逻辑：
  - `ex:UserProfile ex:bindLogic ex:recommend_products`：在用户画像视图上调用“用户推荐产品”逻辑；
  - `ex:ProductCatalog ex:bindLogic ex:match_product_to_users`：在产品目录视图上调用“产品筛选用户群”逻辑；
  - `ex:ContactRecord ex:bindLogic ex:evaluate_campaign`：利用接触记录进行活动效果评估。
- 对象绑定行动：
  - `ex:Campaign ex:bindAction ex:ExecuteTouchAction`：在活动对象上执行触达动作；
  - `ex:ContactRecord ex:bindAction ex:RecordContactHistory`：回填渠道接触历史；
  - `ex:ContactRecord ex:bindAction ex:UpdateConversionStatus`：更新转化状态。

---

## 修订记录
- 1.0（2025-12-19）: 基于 `product_marketing.owl` 结构整理的首版词汇表。
