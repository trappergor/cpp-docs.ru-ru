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
ms.openlocfilehash: c614cbb11376c5ae338762c0feaa54c8f1bb3e27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277935"
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

|name|Описание|
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

*k1*<br/>
Первый ключ.

*k2*<br/>
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
