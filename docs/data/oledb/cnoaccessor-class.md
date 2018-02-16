---
title: "Класс CNoAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9c609a3e15f40311984308c48efbf24d931e188
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
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