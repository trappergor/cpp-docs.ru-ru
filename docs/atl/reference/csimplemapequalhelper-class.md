---
title: Класс CSimpleMapEqualHelper
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: a530254bbaabce723b97d21313abb81e1b375833
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527395"
---
# <a name="csimplemapequalhelper-class"></a>Класс CSimpleMapEqualHelper

Этот класс представляет вспомогательный объект для [CSimpleMap](../../atl/reference/csimplemap-class.md) класса.

## <a name="syntax"></a>Синтаксис

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>Параметры

*TKey*<br/>
Ключевым элементом.

*TVal*<br/>
Значение элемента.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Статический) Проверяет два ключа на равенство.|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Статический) Сравнивает два значения на равенство.|

## <a name="remarks"></a>Примечания

Этот класс признаков является дополнением к `CSimpleMap` класса. Он предоставляет методы для сравнения двух `CSimpleMap` объекта элементов (в частности, ключ и значение компоненты) на предмет равенства. По умолчанию ключи и значения сравниваются с помощью **operator==()**, но если сопоставление содержит сложные типы данных, которые не хватает собственные оператор равенства, этот класс можно переопределить, указав дополнительные необходимые функциональные возможности.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey

Проверяет два ключа на равенство.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Параметры

*K1*<br/>
Первый ключ.

*K2*<br/>
Второй ключ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если ключи равны; значение false в противном случае.

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue

Сравнивает два значения на равенство.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>Параметры

*версии 1*<br/>
Первое значение в вычитании.

*v2*<br/>
Второе значение в вычитании.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если значения равны, значение false в противном случае.

## <a name="see-also"></a>См. также

[Класс CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
