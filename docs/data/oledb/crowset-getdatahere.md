---
title: "CRowset::GetDataHere | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset<TAccessor>::GetDataHere
- CRowset<TAccessor>.GetDataHere
- CRowset.GetDataHere
- GetDataHere
- CRowset::GetDataHere
- ATL::CRowset::GetDataHere
- ATL::CRowset<TAccessor>::GetDataHere
- ATL.CRowset<TAccessor>.GetDataHere
- ATL.CRowset.GetDataHere
dev_langs: C++
helpviewer_keywords: GetDataHere method
ms.assetid: 2fe2a987-1c4c-4299-876e-0591caf63af4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7429ec4b451536d3271432d3822de04ecae7dd87
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetgetdatahere"></a>CRowset::GetDataHere
Извлекает данные из текущей строки и помещает его в указанный буфер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT GetDataHere(   
   int nAccessor,   
   void* pBuffer    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nAccessor`  
 [in] Номер индекса метода доступа для доступа к данным.  
  
 `pBuffer`  
 [out] Буфер, в который требуется добавить данные для текущей записи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Пример использования этой функции см. в разделе [Образец MultiRead](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [CRowset::GetData](../../data/oledb/crowset-getdata.md)