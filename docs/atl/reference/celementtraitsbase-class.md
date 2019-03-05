---
title: Класс CElementTraitsBase
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: 207207d26a2c43367a00b382f80761429159a7b4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263680"
---
# <a name="celementtraitsbase-class"></a>Класс CElementTraitsBase

Этот класс предоставляет копирования по умолчанию и переместить методы для класса коллекции.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CElementTraitsBase::CopyElements](#copyelements)|Этот метод используется для копирования элементов, хранящихся в объекте класса коллекции.|
|[CElementTraitsBase::RelocateElements](#relocateelements)|Этот метод используется для перемещения элементов, сохраненную в объекте класса коллекции.|

## <a name="remarks"></a>Примечания

Этот базовый класс определяет методы для копирования и перемещения элементов в классе коллекции. Он используется классами [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="copyelements"></a>  CElementTraitsBase::CopyElements

Этот метод используется для копирования элементов, хранящихся в объекте класса коллекции.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
Указатель на первый элемент, который будет отправляться скопированные данные.

*pSrc*<br/>
Указатель на первый элемент, для копирования.

*nElements*<br/>
Число элементов для копирования.

### <a name="remarks"></a>Примечания

Исходный и целевой элементы не должны перекрываться.

##  <a name="inargtype"></a>  CElementTraitsBase::INARGTYPE

Тип данных, который нужно использовать для добавления элементов в коллекцию.

```
typedef const T& INARGTYPE;
```

##  <a name="outargtype"></a>  CElementTraitsBase::OUTARGTYPE

Тип данных, который нужно использовать для извлечения элементов из коллекции.

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CElementTraitsBase::RelocateElements

Этот метод используется для перемещения элементов, сохраненную в объекте класса коллекции.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
Указатель на первый элемент, который будет получать перемещенные данные.

*pSrc*<br/>
Указатель на первый элемент, чтобы переместить.

*nElements*<br/>
Число элементов для перемещения.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), что вполне достаточно для большинства типов данных. Если перемещаемый объекты содержат указатели на свои собственные члены, этот метод необходимо переопределить.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
