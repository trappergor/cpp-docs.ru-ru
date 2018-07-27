---
title: PROPERTY_INFO_ENTRY_VALUE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROPERTY_INFO_ENTRY_VALUE
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY_VALUE macro
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbd216a3358385a0a0c1c61e8e3f31a1fd3c8946
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104663"
---
# <a name="propertyinfoentryvalue"></a>PROPERTY_INFO_ENTRY_VALUE
Представляет конкретное свойство в наборе свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID  
, value )  
```  
  
#### <a name="parameters"></a>Параметры  
 *dwPropID*  
 [входные данные] Значение [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.  
  
 *значение*  
 [входные данные] Значение свойства с типом `DWORD`.  
  
## <a name="remarks"></a>Примечания  
 С помощью этого макроса можно напрямую указать значение свойства типа `DWORD`. Чтобы задать свойство, значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать параметры для свойства, флаги и значения, используйте [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).  
  
## <a name="example"></a>Пример  
 См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)