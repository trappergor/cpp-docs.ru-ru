---
title: CRowset::Update | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset.Update
- ATL.CRowset.Update
- ATL.CRowset<TAccessor>.Update
- ATL::CRowset<TAccessor>::Update
- CRowset<TAccessor>::Update
- CRowset::Update
- CRowset<TAccessor>.Update
- ATL::CRowset::Update
dev_langs:
- C++
helpviewer_keywords:
- Update method
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b40486db73d3d545a3226e71a19ba0b588f631ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098138"
---
# <a name="crowsetupdate"></a>CRowset::Update
Передает все ожидающие изменения, внесенные в текущую строку с момента последней выборки или **обновление** вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Update(DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL) throw();  
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