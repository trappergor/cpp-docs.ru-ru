---
title: IDBSchemaRowsetImpl::CheckRestrictions | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
dev_langs:
- C++
helpviewer_keywords:
- CheckRestrictions method
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c951c892a2e6d875fb1085b1d3208d43938347c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106431"
---
# <a name="idbschemarowsetimplcheckrestrictions"></a>IDBSchemaRowsetImpl::CheckRestrictions
Проверяет допустимость ограничений относительно набора строк схемы.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `rguidSchema`  
 [входные данные] Ссылка на запрошенный GUID набора строк схемы (например, `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [входные данные] Число ограничений, переданных потребителем для набора строк схемы.  
  
 `rgRestrictions`  
 [входные данные] Массив длиной *cRestrictions* для задаваемых значений ограничений. Дополнительные сведения см. в описании параметра `rgRestrictions` в [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
## <a name="remarks"></a>Примечания  
 Используйте `CheckRestrictions` для проверки допустимости ограничений для набора строк схемы. Он проверяет ограничения для наборов строк схемы `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**и **DBSCHEMA_PROVIDER_TYPES** . Вызовите для определения правильности вызова **IDBSchemaRowset::GetRowset** . Если необходима поддержка наборов строк схемы, отличных от перечисленных выше, создайте собственную функцию для выполнения этой задачи.  
  
 `CheckRestrictions` определяет, вызывает ли потребитель [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) с правильным ограничением и правильным типом ограничения (например, `VT_BSTR` для строки), поддерживаемыми поставщиком. Он также определяет, поддерживается ли правильное количество ограничений. По умолчанию `CheckRestrictions` будет обращаться к поставщику через вызов [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) , ограничения которого он поддерживает в заданном наборе строк. Затем он сравнит ограничения от потребителя с ограничениями, поддерживаемыми поставщиком. Результатом будет успешное или неудачное выполнение.  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *Справочник программиста OLE DB* в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [Класс IDBSchemaRowsetImpl члены](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)