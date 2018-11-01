---
title: Класс CSimpleMapEqualHelperFalse
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: 7ccfe59e6741c267aded8f59828947a1d98bfbc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572696"
---
# <a name="csimplemapequalhelperfalse-class"></a>Класс CSimpleMapEqualHelperFalse

Этот класс представляет вспомогательный объект для [CSimpleMap](../../atl/reference/csimplemap-class.md) класса.

## <a name="syntax"></a>Синтаксис

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Статический) Проверяет два ключа на равенство.|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Статический) Возвращает значение false.|

## <a name="remarks"></a>Примечания

Этот класс признаков является дополнением к `CSimpleMap` класса. Он предоставляет метод для сравнения двух элементов, содержащихся в `CSimpleMap` объекта, в частности два значения элемента или две ключевые элементы.

Сравнение значений всегда будет возвращать значение false, а кроме того, будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. В ситуациях, где тест на равенство не определен достаточно, этот класс позволяет сопоставление, содержащее пары ключ/значение для правильной работы для большинства методов, но привести к сбою в виде четко определенных для методов, зависящие от сравнения, такие как [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval).

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey

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

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue

Возвращает значение false.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение false.

### <a name="remarks"></a>Примечания

Этот метод всегда возвращает значение false и будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. Цель `CSimpleMapEqualHelperFalse::IsEqualValue` — заставить методы использования сравнений к сбою в виде четко определенных проверок на равенство не определены должным образом.

## <a name="see-also"></a>См. также

[Класс CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
