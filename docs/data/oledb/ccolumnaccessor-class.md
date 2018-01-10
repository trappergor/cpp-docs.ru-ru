---
title: "Класс CColumnAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs: C++
helpviewer_keywords: CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55c77a53cb6e6c4a103c509aa3d527803d91af3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccolumnaccessor-class"></a>Класс CColumnAccessor
Создает код внедренного объекта-получателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Примечания  
 В подставляемый код каждый столбец привязан как отдельный метод доступа. Следует иметь в виду, что этот класс используется в введенного кода (например, вы можете встретить его при отладке), но обычно не требуется непосредственно использовать его, или его методы.  
  
 `CColumnAccessor`реализует следующие заглушки метода, каждый из которых соответствует в функциональных возможностях в другие методы класса метода доступа:  
  
-   `CColumnAccessor`Конструктор. Создает и инициализирует `CColumnAccessor` объекта.  
  
-   `CreateAccessor`Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.  
  
-   **BindColumns** привязывает столбцы к событиям.  
  
-   **SetParameterBuffer** выделяет буферы для параметров.  
  
-   `AddParameter`Добавляет запись параметра запись на параметр структуры.  
  
-   **HasOutputColumns** определяет, является ли метод доступа содержит выходные столбцы  
  
-   **HasParameters** определяет, имеет ли метод доступа параметров.  
  
-   `BindParameters`Привязывает созданные параметры столбцов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)