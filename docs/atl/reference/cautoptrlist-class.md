---
title: Класс CAutoPtrList
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: a7e5c2db31100da8901deaae61527c65655faa7e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551415"
---
# <a name="cautoptrlist-class"></a>Класс CAutoPtrList

Этот класс предоставляет методы, используемые при построении списка интеллектуальные указатели.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Конструктор.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и методы из производного [CAtlList](../../atl/reference/catllist-class.md) и [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) для упрощения создания объекта списка, хранение интеллектуальные указатели. Класс [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) предоставляет ту же функцию для объекта-массива.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="cautoptrlist"></a>  CAutoPtrList::CAutoPtrList

Конструктор.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока по умолчанию 10.

### <a name="remarks"></a>Примечания

Размер блока — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использовать больше ресурсов.

## <a name="see-also"></a>См. также

[Класс CAtlList](../../atl/reference/catllist-class.md)<br/>
[Класс CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
