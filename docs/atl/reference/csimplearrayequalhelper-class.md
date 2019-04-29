---
title: Класс CSimpleArrayEqualHelper
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: 8b7e32ddab5b2f0667b17b0f127ac2e7e5d9a426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277998"
---
# <a name="csimplearrayequalhelper-class"></a>Класс CSimpleArrayEqualHelper

Этот класс представляет вспомогательный объект для [CSimpleArray](../../atl/reference/csimplearray-class.md) класса.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Производный класс.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Статический) Сравнивает два `CSimpleArray` объекта элементов на предмет равенства.|

## <a name="remarks"></a>Примечания

Этот класс признаков является дополнением к `CSimpleArray` класса. Он предоставляет метод для сравнения двух элементов, хранящихся в `CSimpleArray` объекта. По умолчанию элементы сравниваются с помощью **operator=()**, но если массив содержит сложные типы данных, которые не хватает собственные оператор равенства, вам потребуется переопределение этого класса.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual

Сравнивает два `CSimpleArray` объекта элементов на предмет равенства.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Объект типа T.

*T2*<br/>
Объект типа T.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если элементы равны; значение false в противном случае.

## <a name="see-also"></a>См. также

[Класс CSimpleArray](../../atl/reference/csimplearray-class.md)<br/>
[Класс CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
