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
ms.openlocfilehash: 36f5a359051dbd5035a73514f84fb2c61ff13176
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412930"
---
# <a name="idbcreatesessionimpl-class"></a>Класс IDBCreateSessionImpl

Предоставляет реализацию для [IDBCreateSession](/previous-versions/windows/desktop/ms724076(v=vs.85)) интерфейс.

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

См. в разделе [IDBCreateSession::CreateSession](/previous-versions/windows/desktop/ms714942(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)