---
title: Класс CDefaultHashTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: c8896ce27afc40ad095e02a2453628ffc05900da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466148"
---
# <a name="cdefaulthashtraits-class"></a>Класс CDefaultHashTraits

Этот класс предоставляет статическую функцию для вычисления хэш-значения.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDefaultHashTraits::Hash](#hash)|(Статический) Вызывайте эту функцию, для которого требуется вычислить значение хэша для данного элемента.|

## <a name="remarks"></a>Примечания

Этот класс содержит один статическую функцию, которая возвращает значение хэша для данного элемента. Этот класс используется [класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md).

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="hash"></a>  CDefaultHashTraits::Hash

Вызывайте эту функцию, для которого требуется вычислить значение хэша для данного элемента.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает хэш-значение.

### <a name="remarks"></a>Примечания

Алгоритм хэширования по умолчанию очень прост: возвращаемое значение — номер элемента. Переопределите эту функцию, если требуется более сложный алгоритм.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
