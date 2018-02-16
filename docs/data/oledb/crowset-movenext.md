---
title: "CRowset::MoveNext | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.MoveNext
- ATL.CRowset.MoveNext
- ATL::CRowset<TAccessor>::MoveNext
- CRowset<TAccessor>.MoveNext
- CRowset.MoveNext
- CRowset<TAccessor>::MoveNext
- CRowset::MoveNext
- ATL::CRowset::MoveNext
dev_langs:
- C++
helpviewer_keywords:
- MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 981b17597fa8c5c13b528b71f9f26bc4f03a6a02
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
Перемещает курсор к следующей записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT MoveNext() throw();HRESULT MoveNext(LONG lSkip,   
   bool bForward= true) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `lSkip`  
 [in] Количество пропускаемых перед выборкой строк.  
  
 `bForward`  
 [in] Передайте **true** для перемещения вперед к следующей записи **false** для перемещения в обратном направлении.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`. При достижении конца набора строк возвращает **DB_S_ENDOFROWSET**.  
  
## <a name="remarks"></a>Примечания  
 Выбирается следующий последовательный строка из `CRowset` объекта, запоминание предыдущей позиции. При необходимости вы можете пропустить `lSkip` строк или перемещение назад.  
  
 Этот метод необходимо установить следующие свойства перед вызовом **откройте** для таблицы или команду, содержащую набор строк:  
  
-   **DBPROP_CANSCROLLBACKWARDS** должно быть `VARIANT_TRUE` Если `lSkip` < 0  
  
-   **DBPROP_CANFETCHBACKWARDS** должно быть `VARIANT_TRUE` Если `bForward` = false  
  
 В противном случае (если `lSkip` > = 0 и `bForward` = true), необходимо задать дополнительные свойства.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)