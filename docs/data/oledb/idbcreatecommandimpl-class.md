---
title: Класс IDBCreateCommandImpl
ms.date: 11/04/2016
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- IDBCreateCommandImpl::CreateCommand
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
ms.openlocfilehash: 4a4978401ba90e3a7a91ac40cc1b0668adf12ee8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210721"
---
# <a name="idbcreatecommandimpl-class"></a>Класс IDBCreateCommandImpl

Предоставляет реализацию интерфейса [IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>Параметры

*T*<br/>
Объект сеанса, производный от `IDBCreateCommandImpl`.

*коммандкласс*<br/>
Класс команд.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[CreateCommand](#createcommand)|Создает новую команду.|

## <a name="remarks"></a>Remarks

Необязательный интерфейс объекта Session для получения новой команды.

## <a name="idbcreatecommandimplcreatecommand"></a><a name="createcommand"></a>Идбкреатекоммандимпл:: CreateCommand

Создает новую команду и возвращает запрошенный интерфейс.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>Параметры

См. раздел [IDBCreateCommand:: CreateCommand](/previous-versions/windows/desktop/ms709772(v=vs.85)) в *справочнике программиста OLE DB*.

Некоторые параметры соответствуют *OLE DB ссылочным параметрам программиста* с разными именами, которые описаны в разделе `IDBCreateCommand::CreateCommand`.

|OLE DB параметры шаблона|*OLE DB ссылочные параметры программиста*|
|--------------------------------|------------------------------------------------|
|*ппвкомманд*|*ппкомманд*|

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
