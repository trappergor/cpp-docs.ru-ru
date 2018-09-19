---
title: Класс CAutoVectorPtrElementTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8308051d44b0daa0a4691ba825890970762dcc2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036908"
---
# <a name="cautovectorptrelementtraits-class"></a>Класс CAutoVectorPtrElementTraits

Этот класс предоставляет методы, статические функции и определения типов, полезных при создании коллекции с помощью вектора новый интеллектуальных указателей и удалять операторов.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы, статические функции и определения типов для создания объектов класса коллекции, содержащий интеллектуальные указатели. В отличие от [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), этот класс использует векторные новых и удаленных операторах.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="inargtype"></a>  CAutoVectorPtrElementTraits::INARGTYPE

Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

##  <a name="outargtype"></a>  CAutoVectorPtrElementTraits::OUTARGTYPE

Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>См. также

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Класс CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
