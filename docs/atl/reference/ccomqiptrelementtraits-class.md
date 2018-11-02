---
title: Класс CComQIPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: df1bbf5cb36e45b6b47acbd4263c34a7353fd6ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603740"
---
# <a name="ccomqiptrelementtraits-class"></a>Класс CComQIPtrElementTraits

Этот класс предоставляет методы, статические функции и определения типов полезно при создании коллекции указателей интерфейса СОМ.

## <a name="syntax"></a>Синтаксис

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>Параметры

*I*<br/>
COM-интерфейс, указав тип указателя для сохранения.

*piid*<br/>
Указатель на идентификатор IID *я*.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|

## <a name="remarks"></a>Примечания

Этот класс является производным методы и предоставляет полезные typedef, при создании класса коллекции [CComQIPtr](../../atl/reference/ccomqiptr-class.md) указатель интерфейса COM-объектов. Этот класс используется как [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) и [CInterfaceList](../../atl/reference/cinterfacelist-class.md) классы.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="inargtype"></a>  CComQIPtrElementTraits::INARGTYPE

Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>См. также

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
