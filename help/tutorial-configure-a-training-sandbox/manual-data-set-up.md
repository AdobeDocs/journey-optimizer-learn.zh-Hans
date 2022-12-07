---
title: 手动设置数据结构
description: 创建所需的身份命名空间并定义Luma示例数据结构。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: f86140ed3d39462ec245303efecade64a610a938
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 6%

---

# 手动设置数据

在此部分中，您可以创建必需的身份命名空间并定义 [!DNL Luma] 通过创建示例数据结构 [[!UICONTROL 模式]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hans).

>[!TIP]
>观看视频教程 [映射标识](/help/set-up-data/map-identities.md) 开始之前。

## 步骤1:创建身份命名空间

在此步骤中，您可以为 [!DNL Luma] 已命名的自定义标识字段 `lumaLoyaltyId`, `lumaCrmId`和 `lumaProductSKU`. 身份命名空间在构建实时客户配置文件方面起着关键作用，因为同一命名空间中的两个匹配值允许两个数据源形成身份图。

首先，创建 [!UICONTROL 命名空间] 对于 [!DNL Luma Loyalty ID] 架构：

1. 在Journey Optimizer用户界面中，转到***[!UICONTROL 客户]** > **[!UICONTROL 标识]** 中。

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

## 步骤2:创建架构

在此步骤中，通过创建6个示例数据的结构 [[!UICONTROL 模式]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product catalog Schema]](-catalog)

* [[!DNL Luma Product Inventory Events]](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

>[!TIP]
>
>观看视频教程： [创建架构](/help/set-up-data/create-schema.md) 开始之前。

### 创建 [!DNL Luma Loyalty] [!UICONTROL 架构] {#create-luma-loyalty-schema}

#### 创建架构

首先，创建 [!DNL Luma Loyalty] 架构：

1. 转到 **[!UICONTROL 数据管理]** > **[!UICONTROL 模式]** 中。

1. 选择 **[!UICONTROL 创建架构]** 在右上方。

1. 从下拉菜单中，选择 **[!UICONTROL XDM个人配置文件]**，因为您是为单个客户的属性（点、状态等）建模。

   ![创建架构](assets/loyaltyCreateSchema.png)

#### 添加现有字段组

接下来，系统会提示您向架构添加字段组。 必须使用组将所有字段添加到架构。 您正在添加现有字段组，并且必须创建字段组。

>[!NOTE]
>
>如果 [!UICONTROL 字段组] 模式窗口不会在 [!UICONTROL 模式] 页面，选择 **[!UICONTROL 添加]** （如下图所示）。

![添加字段组](assets/add_field_group.png)

1. 在 **[!UICONTROL 添加字段组]** ，请启用以下字段组：

   * **[!UICONTROL 人口统计详细信息]** 用于基本客户数据，如名称和出生日期。

   * **[!UICONTROL 个人联系详细信息]** 有关基本联系人详细信息，如电子邮件地址和电话号码。

   * **[!UICONTROL 忠诚度详细信息]** 对于忠诚度详细信息，如积分、联接日期或状态。 忠诚度字段组在列表中排名靠前，因此最容易搜索它。

1. 选择 **[!UICONTROL 添加字段组]** 将所有三个字段组添加到架构。

   ![选择标准字段组](assets/addstandardFieldGroups.png)

1. 选择架构的顶级节点。

1. 输入 `Luma Loyalty Schema` 作为 [!UICONTROL 显示名称].

#### 创建 [!UICONTROL 字段组]

为帮助确保架构之间的一致性，Adobe建议在一个组中管理所有系统标识符：

1. 从 **[!UICONTROL 组合物]** 部分 [!UICONTROL 字段组]，选择 **[!UICONTROL 添加]**.

1. 选择 **[!UICONTROL 创建新字段组]**.

1. 添加 `Luma Identity Profile Field Group` 作为 **[!UICONTROL 显示名称]**.

1. 添加 `system identifiers for XDM Individual Profile class` 作为 **[!UICONTROL 描述]**.

1. 选择 **[!UICONTROL 添加字段组]**.

   ![创建新字段组](assets/addnewfieldgroup.png)

#### 将字段添加到新 [!UICONTROL 字段组]

新的空字段组将添加到您的架构中。 使用+按钮，您可以向层次结构中的任意位置添加新字段。 在这种情况下，必须在根级别添加字段：

1. 选择 **[!UICONTROL +]** 架构名称旁边。

   此步骤将在 **您的租户id** 命名空间，用于管理自定义字段与任何标准字段之间的冲突。

1. 在 **[!UICONTROL 字段属性]** 侧栏，添加新字段的详细信息：

   * **字段名称:** `systemIdentifier`

   * **[!UICONTROL 显示名称]：**`System Identifier`

   * **类型：** 对象

   * **[!UICONTROL 分配字段组]:** [!DNL Luma identifiers]

1. 选择 **[!UICONTROL 应用]**.

   ![添加系统标识符](assets/addsysteidentifier.png)

   在 `systemIdentifier` 对象：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty ID` | [!UICONTROL 字符串] |
   | `crmId` | `CRM Id` | [!UICONTROL 字符串] |

![字段](./assets/add_fields.png)

#### Set identities

您现在拥有 [!UICONTROL 命名空间] 和 [!DNL Luma Loyalty schema] 已配置。 在摄取数据之前，必须为标识字段添加标签。 与 [!UICONTROL 实时客户资料] 需要指定主标识，并且摄取的每个记录都必须具有该字段的值。

1. 设置 **主标识**:

   从 **[!DNL Luma Loyalty Schema]**:

   1. 选择 **[!DNL Luma Identity Profile Field Group]**。

   2. 选择 **[!DNL loyaltyId]** 字段。

   3. 在 **[!UICONTROL 字段属性]**，启用 **[!UICONTROL 身份]** 框中。

   4. 启用 **[!UICONTROL 主标识]** 框中。

   5. 选择 `Luma Loyalty Id` 命名空间 **[!UICONTROL 身份命名空间]** 下拉列表。

   6. 选择 **[!UICONTROL 应用]**.

      ![主标识](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. 设置 **辅助身份**:

   从 **[!DNL Luma Loyalty Schema]**:

   1. 选择 **[!DNL Luma Identity Profile Field Group]**..

   2. 选择 `crmId` 字段。

   3. 在 **[!UICONTROL 字段属性]**，启用 **[!UICONTROL 身份]** 框中。

   4. 选择 `Luma CRM Id` 命名空间 **[!UICONTROL 身份命名空间]** 下拉列表。

   5. 选择 **[!UICONTROL 应用]**.

#### 为配置文件启用并保存架构

1. 选择架构的顶级节点。

1. 在 [!UICONTROL 字段属性] 启用 **[!UICONTROL 用户档案]**.

   架构应如下所示：

   ![Luma忠诚度架构](assets/lumaloyaltyschema.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

### 创建 [!DNL Luma Product catalog Schema] {#create-luma-product-catalog-schema}


1. 转到 [!UICONTROL 数据管理] -> **[!UICONTROL 模式]** 中。

1. 选择 **[!UICONTROL 创建架构]** 按钮。

1. 从下拉菜单中，选择 **[!UICONTROL 浏览所有架构类型]**，用于创建类。

1. 选择**[!UICONTROL 创建新类].

1. 添加显示名称： `Luma Product Catalog Class`.

1. 分配类。

1. 创建 [!UICONTROL 字段组]:

   * 显示名称： `Luma Product Catalog Field Group`

1. 将以下字段添加到 **[!DNL Luma Product Catalog Field Group]**.

   * 字段名称: `product`

   * 显示名称： `Product`

   * 类型： [!UICONTROL 对象]

   * 字段组: [!DNL Luma Product Catalog Field Group]

1. 选择 **[!UICONTROL 应用]**.

1. 将以下字段添加到 **[!DNL Product]** 对象：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 字符串] |
   | `name` | `Name` | [!UICONTROL 字符串] |
   | `category` | `Category` | [!UICONTROL 字符串] |
   | `color` | `Color` | [!UICONTROL 字符串] |
   | `size` | `Size` | [!UICONTROL 字符串] |
   | `price` | `Price` | [!UICONTROL 双精度] |
   | `description` | `Description` | [!UICONTROL 字符串] |
   | `ImageURL` | `Image URL` | [!UICONTROL 字符串] |
   | `stockQuantity` | `Stock Quantity` | [!UICONTROL 字符串] |

1. 添加 **[!UICONTROL 显示名称]** `Luma Product Catalog Field Group` 到 [!UICONTROL 字段组].

1. 选择&#x200B;**[!UICONTROL 保存]**。


### 创建 [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}


1. 转到 **[!UICONTROL 数据管理]** -> **[!UICONTROL 模式]** 中。

1. 选择 **[!UICONTROL 创建架构]** 按钮。

1. 从下拉菜单中，选择 **[!UICONTROL 浏览所有架构类型]**.

1. 选择 **[!UICONTROL 创建新类]**.

1. 添加显示名称： `Luma Business Event`.

1. 选择类型： *[!UICONTROL 时间系列]*.

1. 分配类。

1. 创建 [!UICONTROL 字段组]:

   * 显示名称： `Product Inventory Event Details`

1. 添加 **[!UICONTROL 显示名称]** `Luma Product Inventory Event Schema` 到架构。

1. 将以下字段添加到Luma Product Info字段组：

   * 字段名称: `inventoryEvent`

   * 显示名称： `Inventory Event`

   * 类型： [!UICONTROL 对象]

   * 字段组: [!DNL Product Inventory Event Details]

1. 将以下字段添加到 **[!DNL Product Inventory Event Details]** 对象：

   | [!UICONTROL 字段名称] | [!UICONTROL 显示名称] | [!UICONTROL 类型] |
   |-------------|-----------|----------|
   | `productId` | `Product ID` | [!UICONTROL 字符串] |
   | `sku` | `SKU` | [!UICONTROL 字符串] |
   | `stockEventType` | `Stock Event Type` | **[!UICONTROL 枚举]** with `restock` 和 `outOfStock` 作为值 |

   1. 设置 `stockEventType` 要枚举，请选择类型： `string`.

   1. 向下滚动到 **[!UICONTROL 字段属性]**.

   1. 启用 **[!UICONTROL 枚举]**.

   1. 输入 **[!UICONTROL 值] ([!UICONTROL label)]**: `restock` (`restock`)。

   1. 选择 **[!UICONTROL 添加行]**.

   1. 输入 **[!UICONTROL 值] ([!UICONTROL label)]**: `outOfStock` (`out of stock`)。

   1. 选择 **[!UICONTROL 应用]**.

      ![枚举](assets/enum.png)

1. 已设置 `productId` 字段 **[!UICONTROL 主标识]** 使用 **[!DNL Luma Product namespace]**.

1. 选择 `sku` 字段，并定义与 `product.sku` 字段 **[!DNL Luma Product catalog Schema]** 架构：

   1. 向下滚动到 **[!UICONTROL 字段属性]**.

   1. 启用 **[!UICONTROL 关系]**.

      1. **[!UICONTROL 参考模式]**: [!DNL Luma Product catalog Schema].

      1. **[!UICONTROL 引用标识命名空间]**: [!DNL Luma Product].
   1. 选择 **[!UICONTROL 应用]**.

      架构应如下所示：

      ![SKU关系](assets/sku_relationship.png)


1. 启用 **用户档案**.

1. 选择 [!UICONTROL 保存] 以保存架构。

### 创建 [!DNL Luma CRM] 和 [!DNL Luma Product Interactions] 模式 {#create-luma-crm-and-luma-product-interactions-schemas}

创建以下其他 [!UICONTROL 模式]:

| [!UICONTROL 显示名称] | [!DNL Luma CRM] | [!DNL Luma Product Interactions] | [!DNL Luma Test Profiles] |
|  ---| ------- | ---- |----|
| **[!UICONTROL 类型]** | [!UICONTROL XDM个人配置文件] | [!UICONTROL XDM体验事件] | [!UICONTROL XDM个人配置文件] |
| **[!UICONTROL 添加现有字段组]** | Luma标识符<br>人口统计详细信息<br>个人联系详细信息 | 身份映射<br>商务详细信息 | Luma标识符<br>人口统计详细信息<br>个人联系详细信息<br>用户档案测试详细信息 |
| **[!UICONTROL 关系]** |  | *[!DNL productListItems.SKU]*:<br> 参考模式 *[!DNL Luma Product catalog Schema]* <br>[!DNL Reference identity namespace] *[!DNL Luma Product]* 模式 |
| **[!UICONTROL 主标识] [!UICONTROL 命名空间])** | systemIdentifier.crmId<br>(Luma CRM Id) |  | personalEmail.address<br>(Email) |
| **[!UICONTROL 次标识] [!UICONTROL 命名空间]** | personalEmail.address(Email)<br>mobilePhone.number(Phone) |  |
| **[!UICONTROL 为配置文件启用]** | 是 | 是 | 是 |

## 后续步骤

现在，您已创建数据结构， [创建数据集和摄取示例数据](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
