---
title: "Класс CSimpleRow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c241118d13f7efecef9413851d3d47ff9a08b58
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="csimplerow-class"></a>Класс CSimpleRow
Предоставляет реализацию по умолчанию для дескриптора строки, которая используется в [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) класса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CSimpleRow  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|Добавляет счетчик ссылок в дескриптор существующей строки.|  
|[Compare](../../data/oledb/csimplerow-compare.md)|Сравнивает две строки, чтобы увидеть, если они ссылаются на один и тот же экземпляр строки.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|Конструктор.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|Освобождает строк.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_dwRef](../../data/oledb/csimplerow-m-dwref.md)|Счетчик ссылок дескриптор существующей строки.|  
|[m_iRowset](../../data/oledb/csimplerow-m-irowset.md)|Индекс для строк, представляющий курсор.|  
  
## <a name="remarks"></a>Примечания  
 Дескриптор строки логически представляет собой уникальный тег для строки результата. `IRowsetImpl` Создает новый `CSimpleRow` для запрашиваемого каждой строки в [IRowsetImpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` Можно также заменить свою собственную реализацию дескриптор строки как аргумент шаблона по умолчанию для `IRowsetImpl`. Единственное требование для замены этого класса заключается в том, чтобы замещающем классе предоставляют конструктор, принимающий один параметр типа **ДЛИННЫЕ**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)