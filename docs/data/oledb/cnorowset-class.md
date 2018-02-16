---
title: "Класс CNoRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs:
- C++
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e8db25fa187d7cf03264fff8b23d96d3b1b0e6f6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cnorowset-class"></a>Класс CNoRowset
Можно использовать в качестве аргумента шаблона (`TRowset`) для [CCommand](../../data/oledb/ccommand-class.md) или [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Класса метода доступа. Значение по умолчанию — `CAccessorBase`.  
  
## <a name="remarks"></a>Примечания  
 Используйте `CNoRowset` как аргумент шаблона, если команда не возвращает набор строк.  
  
 `CNoRowset` реализует следующие заглушки метода, каждый из которых сопоставлен другие методы доступа класса:  
  
-   **BindFinished** -указывает, когда привязка завершена (возвращает `S_OK`).  
  
-   **Закрыть** -освобождает строки и текущий интерфейс IRowset.  
  
-   `GetIID` — Извлекает идентификатор интерфейса точки подключения.  
  
-   **GetInterface** -извлекает интерфейс.  
  
-   `GetInterfacePtr` — Извлекает инкапсулированный указатель на интерфейс.  
  
-   **SetAccessor** -задает указатель для метода доступа.  
  
-   **SetupOptionalRowsetInterfaces** -настраивает дополнительные интерфейсы для набора строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)