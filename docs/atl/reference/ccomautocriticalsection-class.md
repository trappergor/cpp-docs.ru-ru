---
title: Класс CComAutoCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 8cbf08082fd24ef2cf0e8794e2944a799baec084
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321093"
---
# <a name="ccomautocriticalsection-class"></a>Класс CComAutoCriticalSection

`CComAutoCriticalSection`предоставляет методы получения и освобождения права собственности на объект критического раздела.

## <a name="syntax"></a>Синтаксис

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComAutocriticalSection::CcomAutocriticalSection](#ccomautocriticalsection)|Конструктор.|
|[CComAutocriticalSection:::ComAutocriticalSection](#dtor)|Деструктор|

## <a name="remarks"></a>Remarks

`CComAutoCriticalSection`похож на класс [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), за исключением `CComAutoCriticalSection` автоматически инициализирует критический объект раздела в конструкторе.

Как правило, `CComAutoCriticalSection` вы `typedef` используете через имя [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Это имя `CComAutoCriticalSection` ссылается при использовании [CComMultiThreadModel.](../../atl/reference/ccommultithreadmodel-class.md)

Методы `Init` [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) недоступны при использовании этого класса. `Term`

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a>CComAutocriticalSection::CcomAutocriticalSection

Конструктор.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Remarks

Вызывает функцию Win32 [ИнициализироватьCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection), который инициализирует критический объект раздела.

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a>CComAutocriticalSection:::ComAutocriticalSection

Деструктор

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Remarks

Деструктор вызывает [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection), который выпускает все системные ресурсы, используемые критическим объектом раздела.

## <a name="see-also"></a>См. также раздел

[CComFakeCriticalSection класс](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)
