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
ms.openlocfilehash: cff1ca374c9489cb9c5df0dad153c4bf7a4cbc9e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210786"
---
# <a name="idbcreatesessionimpl-class"></a>Класс IDBCreateSessionImpl

Предоставляет реализацию для интерфейса [метода IDBCreateSession](/previous-versions/windows/desktop/ms724076(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class SessionClass>
class ATL_NO_VTABLE IDBCreateSessionImpl
   : public IDBCreateSession
```

### <a name="parameters"></a>Параметры

*T*<br/>
ВАШ КЛАСС, ПРОИЗВОДНЫЙ ОТ

*сессионкласс*<br/>
Объект Session.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[CreateSession](#createsession)|Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс во вновь созданном сеансе.|

## <a name="remarks"></a>Remarks

Обязательный интерфейс для объектов источника данных.

## <a name="idbcreatesessionimplcreatesession"></a><a name="createsession"></a>IDBCreateSessionImpl:: CreateSession

Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс во вновь созданном сеансе.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>Параметры

См. раздел [метода IDBCreateSession:: CreateSession](/previous-versions/windows/desktop/ms714942(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
