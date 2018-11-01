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
ms.openlocfilehash: 5ce4db130f4e8569b666047ca7a5c2bc4e0e6cb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593197"
---
# <a name="irowsetidentityimpl-class"></a>Класс IRowsetIdentityImpl

Реализует OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913) интерфейс, позволяющий тестирования для идентификации строки.

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

См. в разделе [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Чтобы сравнить дескрипторов строк, этот метод приводит `HROW` дескрипторы для `RowClass` члены и вызовы `memcmp` над указателями.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)