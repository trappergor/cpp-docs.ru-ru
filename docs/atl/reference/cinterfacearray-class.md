---
title: Класс CInterfaceArray
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: 2e8714bf40e99a1014d7cd6de82cddb13cbbb9cf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282829"
---
# <a name="cinterfacearray-class"></a>Класс CInterfaceArray

Этот класс предоставляет методы, используемые при создании массива указателей COM-интерфейса.

## <a name="syntax"></a>Синтаксис

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Параметры

*I*<br/>
COM-интерфейс, указав тип указателя для сохранения.

*piid*<br/>
Указатель на идентификатор IID *я*.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Конструктор для интерфейса массива.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и производные методы для создания массива указателей интерфейса СОМ. Используйте [CInterfaceList](../../atl/reference/cinterfacelist-class.md) когда необходима списка.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="cinterfacearray"></a>  CInterfaceArray::CInterfaceArray

Конструктор.

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует этот массив смарт-указатель.

## <a name="see-also"></a>См. также

[Класс CAtlArray](../../atl/reference/catlarray-class.md)<br/>
[Класс CComQIPtr](../../atl/reference/ccomqiptr-class.md)<br/>
[Класс CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
