---
title: Класс CEnumerator | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b7e390212da53f85cb50dd5bb151ea6740784b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096110"
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
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [DBViewer](../../visual-cpp-samples.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)