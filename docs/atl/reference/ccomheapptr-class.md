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
ms.openlocfilehash: eaa21700f63ae07565dba4b8b3b5dabac69e0168
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553742"
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

|Имя|Описание|
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
