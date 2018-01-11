---
title: "CRowset::Update | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Update
- ATL.CRowset.Update
- ATL.CRowset<TAccessor>.Update
- ATL::CRowset<TAccessor>::Update
- CRowset<TAccessor>::Update
- CRowset::Update
- CRowset<TAccessor>.Update
- ATL::CRowset::Update
dev_langs: C++
helpviewer_keywords: Update method
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26cbada107bbefe4c5e32243f2761193b1912a0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetupdate"></a>CRowset::Update
Передает все ожидающие изменения, внесенные в текущую строку с момента последней выборки или **обновление** вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT Update(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `pcRows`  
 [out] Указатель на расположение где **обновление** возвращает количество строк, он пытается обновить, если это необходимо.  
  
 `phRow`  
 [out] Указатель на расположение, где **обновление** возвращает дескриптор строки, он пытается обновить. Если возвращается дескриптор `phRow` имеет значение null.  
  
 `pStatus`  
 [out] Указатель на расположение где **обновление** возвращает значение состояния строк. Состояние не возвращается в том случае, если `pStatus` имеет значение null.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Передает все ожидающие изменения, внесенные в текущую строку с момента последней выборки или обновления этой строки (с помощью **обновление** или [UpdateAll](../../data/oledb/crowset-updateall.md)). Обычно вызывается [SetData](../../data/oledb/crowset-setdata.md) для значения данных по столбцов в строке, а затем вызвать **обновление** для передачи этих изменений.  
  
 Этот метод требует дополнительный интерфейс `IRowsetUpdate`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetUpdate** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)