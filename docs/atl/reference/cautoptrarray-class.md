---
title: Класс CAutoPtrArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23cc8e519fc47173efe413cc687ef48c0dc39945
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025169"
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

|Имя|Описание|
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
