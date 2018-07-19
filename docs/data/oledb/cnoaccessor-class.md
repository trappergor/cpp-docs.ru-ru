---
title: Класс CNoAccessor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3110d20330d42fcb0816873ff3e8a25d1f8436ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097358"
---
# <a name="cnoaccessor-class"></a>Класс CNoAccessor
Можно использовать в качестве аргумента шаблона (`TAccessor`) для шаблона классов, таких как `CCommand` и `CTable`, которых требуется аргумент класса метода доступа.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте `CNoAccessor` как аргумент шаблона, если не хотите, чтобы класс для поддержки параметров или выходные столбцы.  
  
 `CNoAccessor` реализует следующие заглушки метода, каждый из которых сопоставлен другие методы доступа класса:  
  
-   **BindColumns** -привязывает столбцы к событиям.  
  
-   `BindParameters` -Привязывает созданные параметры столбцов.  
  
-   **Привязать** -создает привязок.  
  
-   **Закрыть** -закрывает метода доступа.  
  
-   `ReleaseAccessors` -Освобождает методы доступа, созданный классом.  
  
-   `FreeRecordMemory` -Освобождает все столбцы в текущей записи, которые должны быть освобождены.  
  
-   `GetColumnInfo` — Возвращает сведения о столбцах из открытого набора строк.  
  
-   `GetNumAccessors` — Извлекает число методов доступа, созданный классом.  
  
-   `IsAutoAccessor` — Возвращает значение true, если автоматически извлекаются данные для метода доступа во время операции перемещения.  
  
-   `GetHAccessor` — Извлекает дескриптор метода доступа, указанного метода доступа.  
  
-   `GetBuffer` — Извлекает указатель на буфер закладки.  
  
-   **NoBindOnNullRowset** -предотвращает привязки данных на пустой набор строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)