---
title: "Класс CEnumerator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEnumerator
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0ac9fe73b2d8b37e345ddcf602dd98316eedf46
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cenumerator-class"></a>Класс CEnumerator
Использует объект перечисления OLE DB, который предоставляет [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) интерфейс, чтобы вернуть набор строк, описывающий все источники данных и перечислителей.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Найти](../../data/oledb/cenumerator-find.md)|При поиске с помощью доступных поставщиков (источники данных) поиск с указанным именем.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Извлекает `IMoniker` интерфейс для текущей записи.|  
|[Открыть](../../data/oledb/cenumerator-open.md)|Открывает перечислитель.|  
  
## <a name="remarks"></a>Примечания  
 Вы можете получить **ISourcesRowset** данных косвенно от этого класса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:**atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [DBViewer](../../visual-cpp-samples.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)