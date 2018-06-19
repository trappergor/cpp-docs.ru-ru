---
title: Класс CNoRowset | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87d005dc19ef286bc4b0da927ecabcd90e6f0235
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098164"
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