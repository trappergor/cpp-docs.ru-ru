---
title: "IDBSchemaRowsetImpl::SetRestrictions | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
dev_langs: C++
helpviewer_keywords: SetRestrictions method
ms.assetid: 707d5065-b853-4d38-9b67-3066b4d3b279
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 23d4932508d8abeb96dad1dd0f70e396c7240168
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimplsetrestrictions"></a>IDBSchemaRowsetImpl::SetRestrictions
Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void SetRestrictions(  
   ULONG cRestrictions,  
   GUID* /* rguidSchema */,  
   ULONG* rgRestrictions   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cRestrictions`  
 [входные данные] Число ограничений в массиве `rgRestrictions` и число GUID в массиве `rguidSchema` .  
  
 `rguidSchema`  
 [входные данные] Массив GUID наборов строк схемы, для которого требуется извлечь ограничения. Каждый элемент массива содержит GUID одного набора строк схемы (например, `DBSCHEMA_TABLES`).  
  
 `rgRestrictions`  
 [входные данные] Массив длиной `cRestrictions` для задаваемых значений ограничений. Каждый элемент соответствует ограничениям в наборе строк схемы, определяемом по GUID. Если набор строк схемы не поддерживается поставщиком, элементу присваивается нулевое значение. В противном случае значение **ULONG** значение содержит битовую маску, которая представляет ограничения, поддерживаемые в этом наборе строк схемы. Дополнительные сведения, на котором ограничения соответствуют определенном наборе строк схемы, см. в таблице идентификаторов GUID набора строк схемы в [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *Справочник программиста OLE DB* в Windows ПАКЕТ SDK.  
  
## <a name="remarks"></a>Примечания  
 Объект **IDBSchemaRowset** вызывает `SetRestrictions` для определения ограничений, поддерживаемых в определенном наборе строк схемы (вызывается с помощью [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) через повышенный указатель). Ограничения позволяют выбирать только совпадающие строки (например, поиск всех столбцов в таблице MyTable). Ограничения являются необязательными, и если не поддерживается ни одно ограничение (по умолчанию), всегда возвращаются все данные.  
  
 Реализация по умолчанию этого метода задает элементы массива `rgRestrictions` равными 0. Чтобы задать ограничения, отличные от используемых по умолчанию, нужно переопределить установку по умолчанию в классе сеанса.  
  
 Сведения о реализации поддержки наборов строк схемы см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).  
  
 Пример поставщика, поддерживающего наборы строк схемы, см. в примере [UpdatePV](../../visual-cpp-samples.md) .  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *Справочник программиста OLE DB* в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [Класс IDBSchemaRowsetImpl члены](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Классы схемы Rowset и Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md)   
 [UpdatePV](../../visual-cpp-samples.md)