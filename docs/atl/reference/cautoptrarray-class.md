---
title: Класс CAutoPtrArray
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: beb0184a9945990b8d92efe03d4f54baa76ca380
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246815"
---
# <a name="cautoptrarray-class"></a>Класс CAutoPtrArray

Этот класс предоставляет методы, используемые при создании массива интеллектуальных указателей.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Конструктор.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и методы из производного [CAtlArray](../../atl/reference/catlarray-class.md) и [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) для упрощения создания объекта класса коллекции, хранение интеллектуальные указатели.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="cautoptrarray"></a>  CAutoPtrArray::CAutoPtrArray

Конструктор.

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует этот массив смарт-указатель.

## <a name="see-also"></a>См. также

[Класс CAtlArray](../../atl/reference/catlarray-class.md)<br/>
[Класс CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Класс CAutoPtrList](../../atl/reference/cautoptrlist-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
