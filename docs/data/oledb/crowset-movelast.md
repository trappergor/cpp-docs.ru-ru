---
title: "CRowset::MoveLast | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset<TAccessor>::MoveLast
- CRowset<TAccessor>::MoveLast
- ATL.CRowset.MoveLast
- ATL::CRowset::MoveLast
- CRowset<TAccessor>.MoveLast
- MoveLast
- CRowset::MoveLast
- ATL.CRowset<TAccessor>.MoveLast
- CRowset.MoveLast
dev_langs: C++
helpviewer_keywords: MoveLast method
ms.assetid: 81063578-ae9d-467b-8c88-81d8fc66e020
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d57885232fb10f302aeb36c6c074e7a88f0fb67b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetmovelast"></a>CRowset::MoveLast
Перемещение курсора к последней строке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT MoveLast( ) throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Вызовы [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) для изменения положения расположение next fetch последней позиции и извлекает последнюю строку.  
  
 Этому методу требуется установить **DBPROP_CANSCROLLBACKWARDS** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк. (Для повышения производительности можно также задать **DBPROP_QUICKRESTART** для `VARIANT_TRUE`.)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)