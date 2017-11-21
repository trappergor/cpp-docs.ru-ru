---
title: "IRowsetImpl::GetData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
dev_langs: C++
helpviewer_keywords: GetData method [OLE DB]
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0226a9096a93ae1b0e6cd7705fef773a01eea9f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplgetdata"></a>IRowsetImpl::GetData
Извлекает данные из копии строки в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD( GetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) в *справочника программиста OLE DB*.  
  
 Некоторые параметры соответствуют *Справочник программиста OLE DB* параметры разные имена, которые описаны в **IRowset::GetData**:  
  
|Параметры шаблонов OLE DB|*Справочник программиста OLE DB* параметров|  
|--------------------------------|------------------------------------------------|  
|*pDstData*|`pData`|  
  
## <a name="remarks"></a>Примечания  
 Кроме того, обрабатывает преобразование данных с помощью преобразования данных OLE DB библиотеки DLL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)