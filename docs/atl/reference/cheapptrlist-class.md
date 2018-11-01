---
title: Класс CHeapPtrList
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: ef0224ccb9e2592daecb94204db5e1a8c785c7b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676984"
---
# <a name="cheapptrlist-class"></a>Класс CHeapPtrList

Этот класс предоставляет методы, используемые при построении списка указатели кучи.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<typename E, class Allocator = ATL::CCRTAllocator>
class CHeapPtrList
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип объекта для сохранения в класс коллекции.

*Распределитель*<br/>
Класс выделения памяти для использования. По умолчанию используется [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|Конструктор.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и методы из производного [CAtlList](../../atl/reference/catllist-class.md) и [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) для упрощения создания объекта класса коллекции, хранение указатели кучи.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CAtlList](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="cheapptrlist"></a>  CHeapPtrList::CHeapPtrList

Конструктор.

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Примечания

Размер блока — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использовать больше ресурсов.

## <a name="see-also"></a>См. также

[Класс CAtlList](../../atl/reference/catllist-class.md)<br/>
[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
