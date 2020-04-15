---
title: Класс CAutoPtrArray
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 93fc5cfea4ea655e57e785ca234df59fe10d6570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318896"
---
# <a name="cautoptrarray-class"></a>Класс CAutoPtrArray

Этот класс предоставляет полезные методы при построении массива интеллектуальных указателей.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Конструктор.|

## <a name="remarks"></a>Remarks

Этот класс обеспечивает конструктор и получает методы из [CAtlArray](../../atl/reference/catlarray-class.md) и [CAutoPtrElementTraits,](../../atl/reference/cautoptrelementtraits-class.md) чтобы помочь созданию объекта класса коллекции, хранящих интеллектуальные указатели.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray

Конструктор.

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Remarks

Инициализирует интеллектуальный массив указателей.

## <a name="see-also"></a>См. также раздел

[Класс CAtlArray](../../atl/reference/catlarray-class.md)<br/>
[Класс CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Класс CAutoPtrList](../../atl/reference/cautoptrlist-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
