---
title: Класс CElementTraits
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 646b445aed93c9041932c60442f61792f5e1a7e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245772"
---
# <a name="celementtraits-class"></a>Класс CElementTraits

Этот класс используется классами коллекцию для предоставления методов и функций для перемещения, копирования, сравнения и операций хэширования.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции по умолчанию и методы для перемещения, копирования, сравнение и хэширования элементов, сохраненную в объекте класса коллекции. `CElementTraits` определяется как поставщик по умолчанию из этих операций в классах коллекций [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), и [CRBTree](../../atl/reference/crbtree-class.md).

Реализация по умолчанию будет достаточно для простых типов данных, но если в классах коллекций используются для хранения более сложных объектов, функций и методов должны быть переопределены пользовательские реализации.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="see-also"></a>См. также

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
