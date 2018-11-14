---
title: Класс IConvertTypeImpl
ms.date: 11/04/2016
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
ms.openlocfilehash: 0b3c0f239b3c80d0b4d3c8425b03a3612a0e6db2
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556235"
---
# <a name="iconverttypeimpl-class"></a>Класс IConvertTypeImpl

Предоставляет реализацию [IConvertType](https://docs.microsoft.com/previous-versions/windows/desktop/ms715926(v=vs.85)) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IConvertTypeImpl`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[CanConvert](#canconvert)|Сведения о доступности преобразований типа команды или для набора строк.|

## <a name="remarks"></a>Примечания

Этот интерфейс является обязательным на команды, наборы строк и наборов строк индекса. `IConvertTypeImpl` реализует интерфейс путем делегирования для преобразования объекта, заданного параметром OLE DB.

## <a name="canconvert"></a> IConvertTypeImpl::CanConvert

Сведения о доступности преобразований типа команды или для набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IConvertType::CanConvert](https://docs.microsoft.com/previous-versions/windows/desktop/ms711224(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Использует преобразования данных OLE DB в `MSADC.DLL`.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)