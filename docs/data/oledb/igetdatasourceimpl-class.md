---
title: Класс IGetDataSourceImpl
ms.date: 11/04/2016
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
ms.openlocfilehash: 596dd2ea7f65040ae526662974d210c1f99a0cf2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210617"
---
# <a name="igetdatasourceimpl-class"></a>Класс IGetDataSourceImpl

Предоставляет реализацию объекта [ижетдатасаурце](/previous-versions/windows/desktop/ms709721(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IGetDataSourceImpl`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[GetDataSource](#getdatasource)|Возвращает указатель интерфейса на объекте источника данных, который создал сеанс.|

## <a name="remarks"></a>Remarks

Это обязательный интерфейс в сеансе для получения указателя интерфейса на объект источника данных.

## <a name="igetdatasourceimplgetdatasource"></a><a name="getdatasource"></a>Ижетдатасаурцеимпл:: DataSource

Возвращает указатель интерфейса на объекте источника данных, который создал сеанс.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetDataSource)(REFIID riid,
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>Параметры

См. раздел [ижетдатасаурце:: DataSource](/previous-versions/windows/desktop/ms725443(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Remarks

Полезно, если необходимо получить доступ к свойствам в объекте источника данных.

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
