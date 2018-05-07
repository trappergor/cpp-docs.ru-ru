---
title: Класс IDBCreateSessionImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3e027faa11ec7c2a2b6c8d29ef99fe95419a7594
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="idbcreatesessionimpl-class"></a>Класс IDBCreateSessionImpl
Предоставляет реализацию для [IDBCreateSession](https://msdn.microsoft.com/en-us/library/ms724076.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 КЛАСС, ПРОИЗВОДНЫЙ ОТ  
  
 `SessionClass`  
 Объект сеанса.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[Создание сеанса](../../data/oledb/idbcreatesessionimpl-createsession.md)|Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс на только что созданного сеанса.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс объекты источника данных.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)