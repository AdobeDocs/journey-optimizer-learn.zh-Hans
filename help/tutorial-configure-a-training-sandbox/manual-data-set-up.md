---
title: 手动设置数据结构
description: 创建所需的身份命名空间并定义Luma示例数据结构。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
hide: true
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: 4df1bdca81a585f728aa68519aa7ec7cd0c2f014
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 9%

---

# 手动设置数据

在此部分中，您将创建所需的身份命名空间并定义 [!DNL Luma] 示例数据结构，方法是创建 [[!UICONTROL 架构]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hans).

>[!TIP]
>观看视频教程 [映射身份](/help/set-up-data/map-identities.md) 开始之前。

## 步骤1：创建身份命名空间

在此步骤中，您将为 [!DNL Luma] 命名的自定义身份字段 `lumaLoyaltyId`， `lumaCrmId`、和 `lumaProductSKU`. 身份命名空间在构建实时客户配置文件方面发挥着关键作用，因为同一命名空间中的两个匹配值允许两个数据源形成身份图。

首先创建 [!UICONTROL 命名空间] 对于 [!DNL Luma Loyalty ID] 架构：

1. 在Journey Optimizer用户界面中，转到 **[!UICONTROL 客户]** > **[!UICONTROL 身份]** 左侧导航栏中。

1. 选择 **[!UICONTROL 创建身份命名空间]**.

1. 提供以下详细信息：

   | 显示名称 | 身份符号 | 类型 |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL 跨设备ID] |

1. 选择&#x200B;**[!UICONTROL 创建]**。

   ![创建命名空间](assets/createNamespace.png)

1. 按照相同的步骤再创建两个命名空间：

   | 显示名称 | 身份符号 | 类型 |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL 跨设备ID] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL 非人员标识符] |

## 步骤2：创建架构

在此步骤中，您可以通过创建六个来定义示例数据的结构 [[!UICONTROL 架构]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hans)：

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] 架构](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>观看视频教程： [创建架构](/help/set-up-data/create-schema.md) 开始之前。

### 创建 [!DNL Luma Loyalty Schema] {#create-luma-loyalty-schema}

本节介绍如何创建 [!DNL Luma Loyalty] 架构和配置字段组。

#### 创建架构

1. 转到 **[!UICONTROL 数据管理]** > **[!UICONTROL 架构]** 左侧导航栏中。

1. 选择 **[!UICONTROL 创建架构]** 右上角。

1. 从下拉菜单中，选择 **[!UICONTROL XDM个人资料]**.

   选择此选项，是因为您正在建模单个客户的属性（点、状态等）。

#### 添加现有字段组

接下来，系统会提示您使用组将字段组添加到架构中。 您必须添加现有字段组并创建字段组。

1. 在 [!UICONTROL 架构] 页面，如果字段组模式未自动打开，请选择 **[!UICONTROL 添加]**.

   ![添加字段组](assets/add_field_group.png)

1. 在 **[!UICONTROL 添加字段组]** 页中，启用以下字段组：

   * **[!UICONTROL 人口统计详细信息]** ，以了解名称和出生日期等基本客户数据。

   * **[!UICONTROL 个人联系人详细信息]** 了解电子邮件地址和电话号码等基本联系人详细信息。

   * **[!UICONTROL 忠诚度详细信息]** 积分、加入日期或状态等忠诚度详细信息。 忠诚度字段组在列表中排名靠后，因此搜索它最容易。

1. 选择 **[!UICONTROL 添加字段组]** 以将所有三个字段组添加到架构。

   ![选择标准字段组](assets/addstandardFieldGroups.png)

1. 选择架构的顶级节点。

1. 输入 `Luma Loyalty Schema` 作为 **[!UICONTROL 显示名称]**.

#### 创建 [!UICONTROL 字段组] {#create-field-group}

为帮助确保架构之间的一致性，Adobe建议管理单个组中的所有系统标识符：

1. 从 **[!UICONTROL 合成]** 部分在 [!UICONTROL 字段组]，选择 **[!UICONTROL 添加]**.

1. 选择 **[!UICONTROL 创建新字段组]**.

1. 添加 `Luma Identity Profile Field Group` 作为 **[!UICONTROL 显示名称]**.

1. 添加 `system identifiers for XDM Individual Profile class` 作为 **[!UICONTROL 描述]**.

1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

   ![创建新字段组](assets/addnewfieldgroup.png)

#### 向新添加字段 [!UICONTROL 字段组]

新的空字段组将添加到您的架构中。 使用+按钮，您可以将新字段添加到层次结构中的任意位置。 在这种情况下，您必须在根级别添加字段：

1. 选择 **[!UICONTROL +]** 在架构名称旁边。

   此步骤在下添加一个字段 **您的租户id** 命名空间，用于管理自定义字段和任何标准字段之间的冲突。

1. 在 **[!UICONTROL 字段属性]** 侧栏，添加新字段的详细信息：

   * **字段名称:** `systemIdentifier`

   * **[!UICONTROL 显示名称]：**`System Identifier`

   * **类型：** 对象

   * **[!UICONTROL 分配字段组]：** [!DNL Luma identifiers]

1. 选择&#x200B;**[!UICONTROL 应用]**。

   ![添加系统标识符](assets/addsysteidentifier.png)

   在下面添加两个字段 `systemIdentifier` 对象：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL 字符串] |
   | `crmId` | `CRM Id` | [!UICONTROL 字符串] |

![字段](./assets/add_fields.png)

#### 设置身份

您现在拥有 [!UICONTROL 命名空间] 和 [!DNL Luma Loyalty schema] 已配置。 在摄取数据之前，必须为标识字段添加标签。 使用的每个架构 [!UICONTROL Real-time Customer Profile] 必须指定主标识，并且摄取的每个记录都必须具有该字段的值。

1. 设置 **主要身份**：

   从 **[!DNL Luma Loyalty Schema]**：

   1. 选择 **[!DNL Luma Identity Profile Field Group]**。

   2. 选择 **[!DNL loyaltyId]** 字段。

   3. 在 **[!UICONTROL 字段属性]**，启用 **[!UICONTROL 身份]** 盒子。

   4. 启用 **[!UICONTROL 主要身份]** 盒子。

   5. 选择 `Luma Loyalty Id` 命名空间来自 **[!UICONTROL 身份命名空间]** 下拉菜单。

   6. 选择&#x200B;**[!UICONTROL 应用]**。

      ![主要身份](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. 设置 **辅助标识**：

   从 **[!DNL Luma Loyalty Schema]**：

   1. 选择 **[!DNL Luma Identity Profile Field Group]**。

   2. 选择 `crmId` 字段。

   3. 在 **[!UICONTROL 字段属性]**，启用 **[!UICONTROL 身份]** 盒子。

   4. 选择 `Luma CRM Id` 命名空间来自 **[!UICONTROL 身份命名空间]** 下拉菜单。

   5. 选择&#x200B;**[!UICONTROL 应用]**。

#### 为配置文件启用并保存架构

1. 选择架构的顶级节点。

1. 在 [!UICONTROL 字段属性]，启用 **[!UICONTROL 个人资料]**.

   架构应如下所示：

   ![Luma忠诚度模式](assets/lumaloyaltyschema.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

### 创建 [!DNL Luma Product Catalog Schema] {#create-luma-product-catalog-schema}

1. 转到 **[!UICONTROL 数据管理]** > **[!UICONTROL 架构]** 左侧导航栏中。

1. 选择 **[!UICONTROL 创建架构]** （右上方）。

1. 要创建类，请选择 **[!UICONTROL 浏览所有架构类型]** 下拉菜单中。

1. 选择 **[!UICONTROL 创建新类]**.

1. 添加显示名称： `Luma Product Catalog Class`.

1. 分配类。

1. 创建 [!UICONTROL 字段组]：

   * 显示名称： `Luma Product Catalog Field Group`

1. 将以下字段添加到 **[!DNL Luma Product Catalog Field Group]**.

   * 字段名称: `product`

   * 显示名称： `Product`

   * 类型： [!UICONTROL 对象]

   * 字段组: [!DNL Luma Product Catalog Field Group]

1. 选择&#x200B;**[!UICONTROL 应用]**。

1. 将以下字段添加到 **[!DNL Product]** 对象：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `sku` | `Product SKU` | [!UICONTROL 字符串] |
   | `name` | `Product Name` | [!UICONTROL 字符串] |
   | `category` | `Product Category` | [!UICONTROL 字符串] |
   | `color` | `Product Color` | [!UICONTROL 字符串] |
   | `size` | `Product Size` | [!UICONTROL 字符串] |
   | `price` | `Product Price` | [!UICONTROL 双精度] |
   | `description` | `Product Description` | [!UICONTROL 字符串] |
   | `imageURL` | `Product Image URL` | [!UICONTROL 字符串] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL 字符串] |
   | `url` | `Product URL` | [!UICONTROL 字符串] |

1. 设置 **[!DNL SKU]** 作为主要身份。
1. 添加 **[!UICONTROL 显示名称]** `Luma Product Catalog Field Group` 到 [!UICONTROL 字段组].

1. 选择&#x200B;**[!UICONTROL 保存]**。

### 创建 [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}

1. 转到 **[!UICONTROL 数据管理]** > **[!UICONTROL 架构]** 左侧导航栏中。

1. 选择 **[!UICONTROL 创建架构]** 按钮。

1. 从下拉菜单中，选择 **[!UICONTROL 浏览所有架构类型]**.

1. 选择 **[!UICONTROL 创建新类]**.

1. 添加显示名称： `Luma Business Event Class`.

1. 选择类型： *[!UICONTROL 时间序列]*.

1. 分配类。

1. 创建 [!UICONTROL 字段组]：

   * 显示名称： `Luma Product Inventory Event Details Field Group`

1. 添加 **[!UICONTROL 显示名称]** `Luma Product Inventory Event Schema` 到架构。

1. 将以下字段添加到 **[!DNL Luma Product Inventory Event Details Field Group]**：

   * 字段名称: `inventoryEvent`

   * 显示名称： `Inventory Event`

   * 类型： [!UICONTROL 对象]

   * 字段组: `Luma Product Inventory Event Details Field Group`

1. 将以下字段添加到 `Product Inventory Event Details` 对象：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 字符串] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL 字符串] |

   1. 以设置 `stockEventType` 要枚举，请选择类型： `string`.

   2. 向下滚动到 **[!UICONTROL 字段属性]**.

   3. 启用 **[!UICONTROL 枚举]**.

   4. 输入 **[!UICONTROL 值] ([!UICONTROL label)]**： `restock` (`Restock`)。

   5. 选择 **[!UICONTROL 添加行]**.

   6. 输入 **[!UICONTROL 值] ([!UICONTROL label)]**： `outOfStock` (`Out of Stock`)。

   7. 选择&#x200B;**[!UICONTROL 应用]**。

      ![枚举](assets/enum.png)

1. 设置 `inventory.Event.sku` 字段为 **[!UICONTROL 主要身份]** 使用 **[!DNL LumaProductSKU namespace]**.

1. 选择 `sku` 字段并定义与 `product.sku` 中的字段 **[!DNL Luma Product catalog Schema]** 架构：

   1. 向下滚动到 **[!UICONTROL 字段属性]**.

   2. 启用 **[!UICONTROL 关系]**.

      1. **[!UICONTROL 引用架构]**： [!DNL Luma Product Catalog Schema].

      2. **[!UICONTROL 引用身份命名空间]**： [!DNL LumaProductSKU].
   3. 选择&#x200B;**[!UICONTROL 应用]**。

      架构应如下所示：

      ![SKU关系](assets/sku_relationship.png)


1. 为以下对象启用 **个人资料**.

1. 选择 [!UICONTROL 保存] 以保存架构。

### 创建其他架构 {#create-additional-schemas}

创建以下附加项 [!UICONTROL 架构]：

| [!UICONTROL 显示名称] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL 类]** | [!UICONTROL XDM个人资料] | [!UICONTROL XDM体验事件] | [!UICONTROL XDM个人资料] | [IUICONTROL XDM ExperienceEvent] |
| **[!UICONTROL 添加现有字段组]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL 关系]** |  | `productListItems.SKU`：<br> 引用架构 `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`：<br> 引用架构 `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL 主要身份] [!UICONTROL 命名空间])** | `systemIdentifier.crmId` |  | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL 为配置文件启用]** | 是 | 是 | 是 | 是 |

## 后续步骤

既然您已经创建了数据结构，那么 [创建数据集并摄取示例数据](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
