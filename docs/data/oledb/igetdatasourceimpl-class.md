---
title: Класс IGetDataSourceImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs:
- C++
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7467a658ca8739ba933f266f58e756b8f7a3ba02
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055454"
---
# <a name="igetdatasourceimpl-class"></a>Класс IGetDataSourceImpl

Предоставляет реализацию [IGetDataSource](/previous-versions/windows/desktop/ms709721) объекта.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IGetDataSourceImpl`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[GetDataSource](#getdatasource)|Возвращает указатель интерфейса на объект источника данных, создавшего сеанс.|

## <a name="remarks"></a>Примечания

Это обязательный интерфейс во время сеанса получение указатель интерфейса на объект источника данных.

## <a name="getdatasource"></a> IGetDataSourceImpl::GetDataSource

Возвращает указатель интерфейса на объект источника данных, создавшего сеанс.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetDataSource)(REFIID riid, 
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Полезно, если вам нужно получить доступ к свойствам в объекте источника данных.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)