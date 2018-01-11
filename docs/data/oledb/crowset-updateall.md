---
title: "CRowset::UpdateAll | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset::UpdateAll
- ATL.CRowset.UpdateAll
- CRowset<TAccessor>.UpdateAll
- ATL.CRowset<TAccessor>.UpdateAll
- UpdateAll
- CRowset.UpdateAll
- ATL::CRowset<TAccessor>::UpdateAll
- CRowset<TAccessor>::UpdateAll
- ATL::CRowset::UpdateAll
dev_langs: C++
helpviewer_keywords: UpdateAll method
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 048db34bd08ab3db5769fbcb096578a7a6ae8073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetupdateall"></a>CRowset::UpdateAll
Передает все ожидающие изменения, внесенные во все строки с момента последней выборки или **обновление** вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT UpdateAll(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `pcRows`  
 [out] Указатель на расположение, где `UpdateAll` возвращает количество строк, он пытается обновить, если это необходимо.  
  
 `pphRow`  
 [out] Указатель на буфер, в который `UpdateAll` возвращает дескриптор строки, он пытается обновить. Если возвращается дескриптор `pphRow` имеет значение null.  
  
 `ppStatus`  
 [out] Указатель на расположение где **обновление** возвращает значение состояния строк. Состояние не возвращается в том случае, если `ppStatus` имеет значение null.  
  
## <a name="remarks"></a>Примечания  
 Передает все ожидающие изменения, внесенные во все строки, поскольку эти строки были последней выборки или обновить с помощью [обновление](../../data/oledb/crowset-update.md) или `UpdateAll`. `UpdateAll`будут обновлены все строки, был изменен, независимо от того, по-прежнему имеется ли дескриптор для них (см. `pphRow`) или нет.  
  
 Например, если вы использовали **вставить** вставляется пять строк в наборе строк, может вызвать **обновление** пять раз, либо вызовите `UpdateAll` один раз, чтобы обновить их все.  
  
 Этот метод требует дополнительный интерфейс `IRowsetUpdate`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetUpdate** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)