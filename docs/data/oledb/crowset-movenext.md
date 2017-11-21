---
title: "CRowset::MoveNext | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e2b0a3a3a10ae2cc18ab83800cc50f25903a3607
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
Перемещает курсор к следующей записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
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