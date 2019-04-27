---
title: Класс CComHeapPtr
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: ace8dbb174bd6585e61bd941a60dad28296af72a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246381"
---
# <a name="ccomheapptr-class"></a>Класс CComHeapPtr

Класс смарт-указатель для управления кучей указателей.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта для сохранения в куче.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Конструктор.|

## <a name="remarks"></a>Примечания

`CComHeapPtr` является производным от `CHeapPtr`, но использует [CComAllocator](../../atl/reference/ccomallocator-class.md) для выделения памяти с помощью COM-подпрограммы. См. в разделе [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) для доступных методов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="ccomheapptr"></a>  CComHeapPtr::CComHeapPtr

Конструктор.

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>Параметры

*pData*<br/>
Существующий объект `CComHeapPtr`.

### <a name="remarks"></a>Примечания

Указатель кучи при необходимости могут создаваться с помощью существующего `CComHeapPtr` объекта. Если Да, новый `CComHeapPtr` объект несет ответственность за управление новый указатель и ресурсы.

## <a name="see-also"></a>См. также

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)<br/>
[Класс CComAllocator](../../atl/reference/ccomallocator-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
