---
title: Класс IRowsetIdentityImpl
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: 51f8d7e832476619ccec277c9d73791041d146a6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023183"
---
# <a name="irowsetidentityimpl-class"></a>Класс IRowsetIdentityImpl

Реализует OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85)) интерфейс, позволяющий тестирования для идентификации строки.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetIdentityImpl`.

*RowClass*<br/>
Единица хранения для `HROW`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[IsSameRow](#issamerow)|Сравнение дескрипторов двух строк, чтобы увидеть, если они ссылаются на той же строке.|

## <a name="issamerow"></a> IRowsetIdentityImpl::IsSameRow

Сравнение дескрипторов двух строк, чтобы увидеть, если они ссылаются на той же строке.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Чтобы сравнить дескрипторов строк, этот метод приводит `HROW` дескрипторы для `RowClass` члены и вызовы `memcmp` над указателями.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)