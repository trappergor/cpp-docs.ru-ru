---
title: "Класс CEnumerator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CEnumerator
dev_langs: C++
helpviewer_keywords: CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a64ac02e7b16bfab70966ffaf2a1897ae955f8c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cenumerator-class"></a>Класс CEnumerator
Использует объект перечисления OLE DB, который предоставляет [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) интерфейс, чтобы вернуть набор строк, описывающий все источники данных и перечислителей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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