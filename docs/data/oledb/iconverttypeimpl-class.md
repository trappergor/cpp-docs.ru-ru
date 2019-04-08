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
ms.openlocfilehash: 546a5a007f9e4c1c2a0e581eff2e7984947bdbb5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023728"
---
# <a name="iconverttypeimpl-class"></a>Класс IConvertTypeImpl

Предоставляет реализацию [IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85)) интерфейс.

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

См. в разделе [IConvertType::CanConvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Использует преобразования данных OLE DB в `MSADC.DLL`.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)