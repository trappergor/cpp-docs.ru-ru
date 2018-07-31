---
title: Класс IDBCreateSessionImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 756cc7ba203a1655bf5112d9c03e84707644f1e5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337574"
---
# <a name="idbcreatesessionimpl-class"></a>Класс IDBCreateSessionImpl
Предоставляет реализацию для [IDBCreateSession](https://msdn.microsoft.com/library/ms724076.aspx) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 КЛАСС, ПРОИЗВОДНЫЙ ОТ  
  
 *SessionClass*  
 Объект сеанса.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h 
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[Создание сеанса](#createsession)|Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс на вновь созданный сеанс.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс для объектов источника данных.  

## <a name="createsession"></a> IDBCreateSessionImpl::CreateSession
Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс на вновь созданный сеанс.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IDBCreateSession::CreateSession](https://msdn.microsoft.com/library/ms714942.aspx) в *справочнике программиста OLE DB*.   
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)