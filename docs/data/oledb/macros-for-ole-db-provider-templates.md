---
title: "Макросы для шаблонов поставщика OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.templates.ole
dev_langs: C++
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a61e8156b39b9f0afec477f541920570d4af823
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="macros-for-ole-db-provider-templates"></a>Макросы для шаблонов поставщика OLE DB
Макросы шаблонов поставщик данных OLE DB предоставляют функциональные возможности в следующих категориях:  
  
### <a name="property-set-map-macros"></a>Макросы схемы набора свойств  
  
|||  
|-|-|  
|[BEGIN_PROPERTY_SET](../../data/oledb/begin-property-set.md)|Отмечает начало набора свойств.|  
|[BEGIN_PROPERTY_SET_EX](../../data/oledb/begin-property-set-ex.md)|Отмечает начало набора свойств.|  
|[BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)|Отмечает начало свойство набора, можно скрывать или определен за пределами области поставщика.|  
|[CHAIN_PROPERTY_SET](../../data/oledb/chain-property-set.md)|Объединяются в цепочку группы свойств.|  
|[END_PROPERTY_SET](../../data/oledb/end-property-set.md)|Отмечает конец набора свойств.|  
|[END_PROPSET_MAP](../../data/oledb/end-propset-map.md)|Отмечает конец сопоставление набора свойств.|  
|[PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)|Задает указанное свойство в свойства задано значение по умолчанию.|  
|[PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)|Задает указанное свойство в свойстве присвоено значение, предоставленное пользователем. Также позволяет задать параметры и флаги.|  
|[PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)|Задает указанное свойство в свойстве присвоено значение, предоставленное пользователем.|  
  
### <a name="column-map-macros"></a>Макросы схемы для столбца  
  
|||  
|-|-|  
|[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)|Отмечает начало карты записей столбцов поставщика.|  
|[END_PROVIDER_COLUMN_MAP](../../data/oledb/end-provider-column-map.md)|Отмечает конец карты записей столбцов поставщика.|  
|[PROVIDER_COLUMN_ENTRY](../../data/oledb/provider-column-entry.md)|Представляет отдельного столбца, поддерживаемых поставщиком.|  
|[PROVIDER_COLUMN_ENTRY_GN](../../data/oledb/provider-column-entry-gn.md)|Представляет отдельного столбца, поддерживаемых поставщиком. Можно указать размер столбца, тип данных, точность, масштаб и GUID набора строк схемы.|  
|[PROVIDER_COLUMN_ENTRY_FIXED](../../data/oledb/provider-column-entry-fixed.md)|Представляет отдельного столбца, поддерживаемых поставщиком. Можно указать тип данных столбца.|  
|[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md)|Представляет отдельного столбца, поддерживаемых поставщиком. Можно указать размер столбца.|  
|[PROVIDER_COLUMN_ENTRY_STR](../../data/oledb/provider-column-entry-str.md)|Представляет отдельного столбца, поддерживаемых поставщиком. Предполагается, что типом столбца является строка.|  
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|Представляет отдельного столбца, поддерживаемых поставщиком. PROVIDER_COLUMN_ENTRY_LENGTH, например, но также позволяет указать тип данных столбца, а также размер.|  
|[PROVIDER_COLUMN_ENTRY_WSTR](../../data/oledb/provider-column-entry-wstr.md)|Представляет отдельного столбца, поддерживаемых поставщиком. Предполагается, что столбец имеет тип символьной строки в Юникоде.|  
  
### <a name="schema-rowset-macros"></a>Макросы схемы набора строк  
  
|||  
|-|-|  
|[BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)|Отмечает начало карты схемы.|  
|[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)|Связывает GUID с классом.|  
|[END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)|Отмечает конец карты схемы.|  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)   
 [Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)