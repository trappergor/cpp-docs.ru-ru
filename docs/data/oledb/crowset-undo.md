---
title: "CRowset::Undo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Undo
- ATL::CRowset<TAccessor>::Undo
- CRowset<TAccessor>::Undo
- ATL.CRowset.Undo
- ATL.CRowset<TAccessor>.Undo
- CRowset<TAccessor>.Undo
- ATL::CRowset::Undo
- CRowset::Undo
- Undo
dev_langs:
- C++
helpviewer_keywords:
- Undo method
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 505efd2ede7a436d56f32fcc1915f8c18b9a8b55
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetundo"></a>CRowset::Undo
Отменяет все изменения, внесенные в строку с момента последней выборки или [обновление](../../data/oledb/crowset-update.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Undo(DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `pcRows`  
 [out] Указатель на расположение где **отменить** возвращает количество строк, она была предпринята попытка отмены при необходимости.  
  
 `phRow`  
 [out] Указатель на расположение, где **отменить** возвращает массив дескрипторов ко всем строкам, она была предпринята попытка отмены при необходимости.  
  
 `pStatus`  
 [out] Указатель на расположение, где **отменить** возвращает значение состояния строк. Состояние не возвращается в том случае, если `pStatus` имеет значение null.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод требует дополнительный интерфейс `IRowsetUpdate`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetUpdate** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)