---
title: Класс CHeapPtrList | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0e44475d7d9eee547e0e9d47c8d49c439d91bd1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766624"
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

*E*  
Тип объекта для сохранения в класс коллекции.

*Распределитель*  
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

*nBlockSize*  
Размер блока.

### <a name="remarks"></a>Примечания

Размер блока — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использовать больше ресурсов.

## <a name="see-also"></a>См. также

[Класс CAtlList](../../atl/reference/catllist-class.md)   
[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
[Класс CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
