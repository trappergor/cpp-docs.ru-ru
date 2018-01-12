---
title: "CRowset::SetData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.SetData
- SetData
- ATL::CRowset::SetData
- CRowset<TAccessor>.SetData
- CRowset::SetData
- ATL.CRowset.SetData
- CRowset.SetData
- CRowset<TAccessor>::SetData
- ATL::CRowset<TAccessor>::SetData
dev_langs: C++
helpviewer_keywords: SetData method
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0aafc521e130a7f737083390fe5f825c88aa5844
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetsetdata"></a>CRowset::SetData
Задает значения данных в один или несколько столбцов строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nAccessor`  
 [in] Номер доступа, используемый для доступа к данным.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Для `SetData` форму, которая принимает аргументы, все методы доступа используются для обновления. Обычно вызывается **SetData** для задания значений данных в столбцах в строке, затем вызовите [обновление](../../data/oledb/crowset-update.md) для передачи этих изменений.  
  
 Этот метод требует дополнительный интерфейс `IRowsetChange`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetChange** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
 Операции настройки может завершиться ошибкой, если один или несколько столбцов не может быть перезаписан. Измените схему курсоров, чтобы исправить это.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)