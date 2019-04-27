---
title: Класс CAutoPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: d217441048403b0ff5361f8049b76367174812f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246745"
---
# <a name="cautoptrelementtraits-class"></a>Класс CAutoPtrElementTraits

Этот класс предоставляет методы, статические функции и определения типов полезно при создании коллекции интеллектуальных указателей.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы, статические функции и определения типов для создания объектов класса коллекции, содержащий интеллектуальные указатели. Классы [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) и [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) являются производными от `CAutoPtrElementTraits`. Если для создания коллекции интеллектуальных указателей, который требуется вектор new и delete операторы, использовать [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) вместо этого.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="inargtype"></a>  CAutoPtrElementTraits::INARGTYPE

Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.

```
typedef CAutoPtr<T>& INARGTYPE;
```

##  <a name="outargtype"></a>  CAutoPtrElementTraits::OUTARGTYPE

Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>См. также

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
