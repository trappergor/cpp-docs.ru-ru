---
title: "IRowsetChangeImpl::FlushData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs: C++
helpviewer_keywords: FlushData method
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 565b971b53ddb0a50b276d76aaaf62e9f7fa39f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetchangeimplflushdata"></a>IRowsetChangeImpl::FlushData
Overidden поставщиком для фиксации данных к своему хранилищу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *hRowToFlush*  
 [in] Дескриптор строки данных. Тип этой строки определяется по *RowClass* аргумент шаблона `IRowsetImpl` класса (`CSimpleRow` по умолчанию).  
  
 *hAccessorToFlush*  
 [in] Дескриптор для доступа, который содержит сведения о привязке и сведения о типе в его **PROVIDER_MAP** (см. [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)