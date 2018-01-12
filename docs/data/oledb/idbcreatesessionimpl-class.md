---
title: "Класс IDBCreateSessionImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
dev_langs: C++
helpviewer_keywords: IDBCreateSessionImpl class
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5f8cb4e35c14ddbb8a7f8df3fe3686025cf5eae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="idbcreatesessionimpl-class"></a>Класс IDBCreateSessionImpl
Предоставляет реализацию для [IDBCreateSession](https://msdn.microsoft.com/en-us/library/ms724076.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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