---
title: Класс IRowsetCreatorImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0492994193130ffa6a547691490b4da1ae557c8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetcreatorimpl-class"></a>Класс IRowsetCreatorImpl
Выполняет те же функции, как `IObjectWithSite` , но и обеспечивает свойства OLE DB **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от **IRowsetCreator**.  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|Задает сайт, который содержит объект набора строк.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс наследует от [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) и переопределяет [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). Если объект команды или сеанса поставщика создает набор строк, он вызывает `QueryInterface` в объекте набора строк, поиск `IObjectWithSite` и вызывает метод `SetSite` передачи объекта набора строк **IUnkown** интерфейс как интерфейс веб-сайта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)