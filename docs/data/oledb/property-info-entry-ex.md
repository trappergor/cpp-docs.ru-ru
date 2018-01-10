---
title: "PROPERTY_INFO_ENTRY_EX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROPERTY_INFO_ENTRY_EX
dev_langs: C++
helpviewer_keywords: PROPERTY_INFO_ENTRY_EX macro
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0aae37cad8119133c468c1f635abca6ff69c5757
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="propertyinfoentryex"></a>PROPERTY_INFO_ENTRY_EX
Представляет конкретное свойство в наборе свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
PROPERTY_INFO_ENTRY_EX(  
dwPropID  
, vt, dwFlags, value, options )  
```  
  
#### <a name="parameters"></a>Параметры  
 *dwPropID*  
 [входные данные] Значение [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.  
  
 *vt*  
 [входные данные] [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) этой записи свойства.  
  
 `dwFlags`  
 [входные данные] Значение [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) , описывающее эту запись свойства.  
  
 *значение*  
 [входные данные] Значение свойства с типом `DWORD`.  
  
 `options`  
 **DBPROPOPTIONS_REQUIRED** или **DBPROPOPTIONS_SETIFCHEAP**. Как правило, поставщику не нужно задавать `options` , так как он задан потребителем.  
  
## <a name="remarks"></a>Примечания  
 С помощью этого макроса можно напрямую указать значение свойства типа `DWORD` , а также параметры и флаги. Чтобы задать свойству значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать свойству значение по своему усмотрению без параметров или флагов, используйте [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## <a name="example"></a>Пример  
 См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)