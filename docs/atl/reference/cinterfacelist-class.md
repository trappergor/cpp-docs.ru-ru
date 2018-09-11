---
title: Класс CInterfaceList | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9b0eb225f9da88db356fc4f04d25d2219876604
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752753"
---
# <a name="cinterfacelist-class"></a>Класс CInterfaceList

Этот класс предоставляет методы, используемые при построении списка указателей интерфейса СОМ.

## <a name="syntax"></a>Синтаксис

```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Параметры

*I*  
COM-интерфейс, указав тип указателя для сохранения.

*piid*  
Указатель на идентификатор IID *я*.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Конструктор для списке интерфейсов.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и производные методы для создания списка указателей интерфейса СОМ. Используйте [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) когда необходима массив.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="cinterfacelist"></a>  CInterfaceList::CInterfaceList

Конструктор для списке интерфейсов.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*  
Размер блока по умолчанию 10.

### <a name="remarks"></a>Примечания

Размер блока — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использовать больше ресурсов.

## <a name="see-also"></a>См. также

[Класс CAtlList](../../atl/reference/catllist-class.md)   
[Класс CComQIPtr](../../atl/reference/ccomqiptr-class.md)   
[Класс CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
