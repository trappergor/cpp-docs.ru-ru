---
title: Класс CColumnAccessor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs:
- C++
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d211277a8354d94f1892b97ea8f808cc0b22c30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095324"
---
# <a name="ccolumnaccessor-class"></a>Класс CColumnAccessor
Создает код внедренного объекта-получателя.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Примечания  
 В подставляемый код каждый столбец привязан как отдельный метод доступа. Следует иметь в виду, что этот класс используется в введенного кода (например, вы можете встретить его при отладке), но обычно не требуется непосредственно использовать его, или его методы.  
  
 `CColumnAccessor` реализует следующие заглушки метода, каждый из которых соответствует в функциональных возможностях в другие методы класса метода доступа:  
  
-   `CColumnAccessor` Конструктор. Создает и инициализирует `CColumnAccessor` объекта.  
  
-   `CreateAccessor` Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.  
  
-   **BindColumns** привязывает столбцы к событиям.  
  
-   **SetParameterBuffer** выделяет буферы для параметров.  
  
-   `AddParameter` Добавляет запись параметра запись на параметр структуры.  
  
-   **HasOutputColumns** определяет, является ли метод доступа содержит выходные столбцы  
  
-   **HasParameters** определяет, имеет ли метод доступа параметров.  
  
-   `BindParameters` Привязывает созданные параметры столбцов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)