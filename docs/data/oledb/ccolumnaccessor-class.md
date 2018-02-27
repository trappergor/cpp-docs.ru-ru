---
title: "Класс CColumnAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa03f7ee652ee176c7333ac5ef4e264b7f4d5cf8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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