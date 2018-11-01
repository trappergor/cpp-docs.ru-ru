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
ms.openlocfilehash: dffd15478f0ae10d42b49be3b202fbd4845abb56
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544655"
---
# <a name="iconverttypeimpl-class"></a>Класс IConvertTypeImpl

Предоставляет реализацию [IConvertType](/previous-versions/windows/desktop/ms715926) интерфейс.

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

См. в разделе [IConvertType::CanConvert](/previous-versions/windows/desktop/ms711224) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Использует преобразования данных OLE DB в `MSADC.DLL`.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)