---
title: Класс IRowsetIdentityImpl
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: 3e8c976fcb23bf41d88d88be3887db4dde52379d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545897"
---
# <a name="irowsetidentityimpl-class"></a>Класс IRowsetIdentityImpl

Реализует интерфейс OLE DB [ировсетидентити](/previous-versions/windows/desktop/ms715913(v=vs.85)) , который позволяет выполнять проверку подлинности строк.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetIdentityImpl`.

*ровкласс*<br/>
Единица хранения для `HROW`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[IsSameRow](#issamerow)|Сравнивает два дескриптора строки, чтобы определить, ссылаются ли они на одну и ту же строку.|

## <a name="irowsetidentityimplissamerow"></a><a name="issamerow"></a>IRowsetIdentityImpl:: IsSameRow

Сравнивает два дескриптора строки, чтобы определить, ссылаются ли они на одну и ту же строку.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>Параметры

См. раздел [ировсетидентити:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Для сравнения дескрипторов строк этот метод приводит `HROW` дескрипторы к `RowClass`ным элементам и вызывает `memcmp` для указателей.

## <a name="see-also"></a>См. также:

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)