---
title: 手动设置数据结构
description: 创建所需的身份命名空间并定义 Luma 样本数据结构。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: d848272dba814c300aa21110316b5b37ccb719ce
workflow-type: ht
source-wordcount: '1021'
ht-degree: 100%

---

# 手动设置数据

在此部分中，您将创建所需的身份命名空间并通过创建[[!UICONTROL 架构]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hans)来定义 [!DNL Luma] 样本数据结构。

>[!TIP]
>在开始之前，请观看视频教程[映射标示](/help/data-management/map-identities.md)。

## 步骤 1：创建身份命名空间

在此步骤中，您将为 [!DNL Luma] 自定义身份字段（命名为 `lumaLoyaltyId`、`lumaCrmId` 和 `lumaProductSKU`）创建身份命名空间。身份命名空间在构建实时客户个人资料方面发挥着关键作用，因为同一命名空间的两个匹配值会让两个数据源形成身份图。

首先为 [!DNL Luma Loyalty ID] 架构创建[!UICONTROL 命名空间]：

1. 在 Journey Optimizer 用户界面中，在左侧导航栏中转到&#x200B;**[!UICONTROL 客户]** > **[!UICONTROL 身份]**。

1. 选择&#x200B;**[!UICONTROL 创建身份命名空间]**。

1. 提供以下详细信息：

   | 显示名称 | 身份符号 | 类型 |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL 跨设备 ID] |

1. 选择&#x200B;**[!UICONTROL 创建]**。

   ![创建命名空间](assets/createNamespace.png)

1. 按照相同的步骤再创建两个命名空间：

   | 显示名称 | 身份符号 | 类型 |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL 跨设备 ID] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL 非人员标识符] |

## 步骤 2：创建架构

在此步骤中，您将通过创建六个[[!UICONTROL 架构]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hans)来定义样本数据的结构：

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] 架构](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>在开始之前，请观看视频教程：[创建架构](/help/data-management/create-schema.md)。

### 创建 [!DNL Luma Loyalty Schema] {#create-luma-loyalty-schema}

此部分介绍如何创建 [!DNL Luma Loyalty] 架构和配置字段组。

#### 创建架构

1. 在左侧导航栏中转到&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 架构]**。

1. 选择右上角的&#x200B;**[!UICONTROL 创建架构]**。

1. 从下拉菜单中，选择 **[!UICONTROL XDM 个人资料]**。

   选择此选项，是因为您正在针对单个客户的属性（积分、状态等）进行建模。

#### 添加现有字段组

接下来，系统会提示您使用组将字段组添加到架构中。您必须添加现有字段组并创建字段组。

1. 在[!UICONTROL 架构]页面上，如果字段组模式未自动打开，请选择&#x200B;**[!UICONTROL 添加]**。

   ![添加字段组](assets/add_field_group.png)

1. 在&#x200B;**[!UICONTROL 添加字段组]**&#x200B;页面上，启用以下字段组：

   * **[!UICONTROL 人口统计详细信息]**，用于获取姓名和出生日期等基本客户数据。

   * **[!UICONTROL 个人联系方式]**，用于获取电子邮件地址和电话号码等基本联系信息。

   * **[!UICONTROL 忠诚度详细信息]**，用于获取积分、加入日期或状态等忠诚度详细信息。忠诚度字段组在列表中排名靠后，因此找到它的最简便方式是进行搜索。

1. 选择&#x200B;**[!UICONTROL 添加字段组]**，以便将所有三个字段组添加到架构。

   ![选择标准字段组](assets/addstandardFieldGroups.png)

1. 选择架构的顶级节点。

1. 输入 `Luma Loyalty Schema` 作为&#x200B;**[!UICONTROL 显示名称]**。

#### 创建[!UICONTROL 字段组] {#create-field-group}

为帮助确保架构间的一致性，Adobe 建议在单个组中管理所有系统标识符：

1. 从[!UICONTROL 字段组]下的&#x200B;**[!UICONTROL 组合]**&#x200B;部分，选择&#x200B;**[!UICONTROL 添加]**。

1. 选择&#x200B;**[!UICONTROL 创建新字段组]**。

1. 添加 `Luma Identity Profile Field Group` 作为&#x200B;**[!UICONTROL 显示名称]**。

1. 添加 `system identifiers for XDM Individual Profile class` 作为&#x200B;**[!UICONTROL 描述]**。

1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

   ![创建新字段组](assets/addnewfieldgroup.png)

#### 将字段添加到新[!UICONTROL 字段组]

新的空字段组将会添加到您的架构中。使用“+”按钮，您可以将新字段添加到层级中的任意位置。在此示例中，您必须在根级别添加字段：

1. 选择架构名称旁边的 **[!UICONTROL +]**。

   此步骤会在&#x200B;**您的租户 id** 命名空间下添加一个字段，以管理自定义字段和任何标准字段之间的冲突。

1. 在&#x200B;**[!UICONTROL 字段属性]**&#x200B;侧栏中，添加新字段的详细信息：

   * **字段名称：** `systemIdentifier`

   * **[!UICONTROL 显示名称]：**`System Identifier`

   * **类型：**&#x200B;对象

   * **[!UICONTROL 分配字段组]：**[!DNL Luma identifiers]

1. 选择&#x200B;**[!UICONTROL 应用]**。

   ![添加系统标识符](assets/addsysteidentifier.png)

   在 `systemIdentifier` 对象下添加两个字段：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL 字符串] |
   | `crmId` | `CRM Id` | [!UICONTROL 字符串] |

![字段](./assets/add_fields.png)

#### 设置身份

您现在已完成[!UICONTROL 命名空间]和 [!DNL Luma Loyalty schema] 的配置。在摄取数据之前，必须为身份字段添加标签。配合 [!UICONTROL Real-time Customer Profile] 使用的每个架构都必须指定主要身份，并且摄取的每条记录都必须具有该字段的值。

1. 设置&#x200B;**主要身份**：

   从 **[!DNL Luma Loyalty Schema]**：

   1. 选择 **[!DNL Luma Identity Profile Field Group]**。

   2. 选择 **[!DNL loyaltyId]** 字段。

   3. 在&#x200B;**[!UICONTROL 字段属性]**&#x200B;中，启用&#x200B;**[!UICONTROL 身份]**&#x200B;复选框。

   4. 启用&#x200B;**[!UICONTROL 主要身份]**&#x200B;复选框。

   5. 从&#x200B;**[!UICONTROL 身份命名空间]**&#x200B;下拉菜单中选择 `Luma Loyalty Id` 命名空间。

   6. 选择&#x200B;**[!UICONTROL 应用]**。

      ![主要身份](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. 设置&#x200B;**次要身份**：

   从 **[!DNL Luma Loyalty Schema]**：

   1. 选择 **[!DNL Luma Identity Profile Field Group]**。

   2. 选择 `crmId` 字段。

   3. 在&#x200B;**[!UICONTROL 字段属性]**&#x200B;中，启用&#x200B;**[!UICONTROL 身份]**&#x200B;复选框。

   4. 从&#x200B;**[!UICONTROL 身份命名空间]**&#x200B;下拉菜单中选择 `Luma CRM Id` 命名空间。

   5. 选择&#x200B;**[!UICONTROL 应用]**。

#### 为个人资料启用并保存架构

1. 选择架构的顶级节点。

1. 在[!UICONTROL 字段属性]中，启用&#x200B;**[!UICONTROL 个人资料]**。

   架构应如下所示：

   ![Luma 忠诚度架构](assets/lumaloyaltyschema.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

### 创建 [!DNL Luma Product Catalog Schema] {#create-luma-product-catalog-schema}

1. 在左侧导航栏中转到&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 架构]**。

1. 选择&#x200B;**[!UICONTROL 创建架构]**（右上方）。

1. 要创建类，请在下拉菜单中选择&#x200B;**[!UICONTROL 浏览所有架构类型]**。

1. 选择&#x200B;**[!UICONTROL 创建新类]**。

1. 添加显示名称：`Luma Product Catalog Class`。

1. 分配类。

1. 创建[!UICONTROL 字段组]：

   * 显示名称：`Luma Product Catalog Field Group`

1. 将以下字段添加到 **[!DNL Luma Product Catalog Field Group]**。

   * 字段名称：`product`

   * 显示名称：`Product`

   * 类型：[!UICONTROL 对象]

   * 字段组：[!DNL Luma Product Catalog Field Group]

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
   | `imageUrl` | `Product Image URL` | [!UICONTROL 字符串] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL 字符串] |
   | `url` | `Product URL` | [!UICONTROL 字符串] |

1. 将 **[!DNL SKU]** 设置为主要身份。
1. 将&#x200B;**[!UICONTROL 显示名称]** `Luma Product Catalog Field Group` 添加到[!UICONTROL 字段组]。

1. 选择&#x200B;**[!UICONTROL 保存]**。

### 创建 [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}

1. 在左侧导航栏中转到&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 架构]**。

1. 选择右上角的&#x200B;**[!UICONTROL 创建架构]**&#x200B;按钮。

1. 从下拉菜单中，选择&#x200B;**[!UICONTROL 浏览所有架构类型]**。

1. 选择&#x200B;**[!UICONTROL 创建新类]**。

1. 添加显示名称：`Luma Business Event Class`。

1. 选择类型：*[!UICONTROL 时间序列]*。

1. 分配类。

1. 创建[!UICONTROL 字段组]：

   * 显示名称：`Luma Product Inventory Event Details Field Group`

1. 将&#x200B;**[!UICONTROL 显示名称]** `Luma Product Inventory Event Schema` 添加到架构。

1. 将以下字段添加到 **[!DNL Luma Product Inventory Event Details Field Group]**：

   * 字段名称：`inventoryEvent`

   * 显示名称：`Inventory Event`

   * 类型：[!UICONTROL 对象]

   * 字段组：`Luma Product Inventory Event Details Field Group`

1. 将以下字段添加到 `Product Inventory Event Details` 对象：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 字符串] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL 字符串] |

   1. 要将 `stockEventType` 设置为“枚举”，请选择类型：`string`。

   2. 向下滚动到&#x200B;**[!UICONTROL 字段属性]**&#x200B;的底部。

   3. 启用&#x200B;**[!UICONTROL 枚举]**。

   4. 输入&#x200B;**[!UICONTROL 值]（[!UICONTROL 标签）]**：`restock` (`Restock`)。

   5. 选择&#x200B;**[!UICONTROL 添加行]**。

   6. 输入&#x200B;**[!UICONTROL 值]（[!UICONTROL 标签）]**：`outOfStock` (`Out of Stock`)。

   7. 选择&#x200B;**[!UICONTROL 应用]**。

      ![枚举](assets/enum.png)

1. 使用 **[!DNL LumaProductSKU namespace]** 将 `inventory.Event.sku` 字段设置为&#x200B;**[!UICONTROL 主要身份]**。

1. 选择 `sku` 字段并在 **[!DNL Luma Product catalog Schema]** 架构中定义其与 `product.sku` 字段的关系：

   1. 向下滚动到&#x200B;**[!UICONTROL 字段属性]**&#x200B;的底部。

   2. 启用&#x200B;**[!UICONTROL 关系]**。

      1. **[!UICONTROL 引用架构]**：[!DNL Luma Product Catalog Schema]。

      2. **[!UICONTROL 引用身份命名空间]**：[!DNL LumaProductSKU]。

   3. 选择&#x200B;**[!UICONTROL 应用]**。

      架构应如下所示：

      ![SKU 关系](assets/sku_relationship.png)

1. 为&#x200B;**个人资料**&#x200B;启用。

1. 选择[!UICONTROL 保存]以保存架构。

### 创建其他架构 {#create-additional-schemas}

创建以下其他[!UICONTROL 架构]：

| [!UICONTROL 显示名称] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL 类]** | [!UICONTROL XDM 个人资料] | [!UICONTROL XDM 体验活动] | [!UICONTROL XDM 个人资料] | [IUICONTROL XDM ExperienceEvent] |
| **[!UICONTROL 添加现有字段组]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL 关系]** |  | `productListItems.SKU`：<br>引用架构 `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`：<br>引用架构 `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL 主要身份][!UICONTROL 命名空间]）** | `systemIdentifier.crmId` | | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL 为个人资料启用]** | 是 | 是 | 是 | 是 |

## 后续步骤

现在您已创建数据结构，您可以[创建数据集并摄取样本数据](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md)。
