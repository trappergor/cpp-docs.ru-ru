---
title: Класс CElementTraitsBase | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1943895b8db663239ed1bfb27b8e97fc3c416e5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767910"
---
# <a name="celementtraitsbase-class"></a>Класс CElementTraitsBase

Этот класс предоставляет копирования по умолчанию и переместить методы для класса коллекции.

## <a name="syntax"></a>Синтаксис

```
template<typename T>  
class CElementTraitsBase
```

#### <a name="parameters"></a>Параметры

*T*  
Тип данных, хранимых в коллекции.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
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

*pDest*  
Указатель на первый элемент, который будет отправляться скопированные данные.

*pSrc*  
Указатель на первый элемент, для копирования.

*nElements*  
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

*pDest*  
Указатель на первый элемент, который будет получать перемещенные данные.

*pSrc*  
Указатель на первый элемент, чтобы переместить.

*nElements*  
Число элементов для перемещения.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), что вполне достаточно для большинства типов данных. Если перемещаемый объекты содержат указатели на свои собственные члены, этот метод необходимо переопределить.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
