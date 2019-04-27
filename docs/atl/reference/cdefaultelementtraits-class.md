---
title: Класс CDefaultElementTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: 0ee076af5fc4a1c2145162ac510b3a4460e251e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245938"
---
# <a name="cdefaultelementtraits-class"></a>Класс CDefaultElementTraits

Этот класс предоставляет функции и методы по умолчанию для класса коллекции.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции по умолчанию и методы для перемещения, копирования, сравнение и хэширования элементов, сохраненную в объекте класса коллекции. Этот класс является производным, его функции и методы из [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), и [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)и используемой [ CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), и [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
