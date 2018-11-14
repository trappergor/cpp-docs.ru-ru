---
title: Класс IDBCreateSessionImpl
ms.date: 11/04/2016
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
ms.openlocfilehash: ecc06bf5e3514ea87c86de17dbafd59b9da9f8b6
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556426"
---
# <a name="idbcreatesessionimpl-class"></a>Класс IDBCreateSessionImpl

Предоставляет реализацию для [IDBCreateSession](https://docs.microsoft.com/previous-versions/windows/desktop/ms724076(v=vs.85)) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class SessionClass>
class ATL_NO_VTABLE IDBCreateSessionImpl
   : public IDBCreateSession
```

### <a name="parameters"></a>Параметры

*T*<br/>
КЛАСС, ПРОИЗВОДНЫЙ ОТ

*SessionClass*<br/>
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

См. в разделе [IDBCreateSession::CreateSession](https://docs.microsoft.com/previous-versions/windows/desktop/ms714942(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)