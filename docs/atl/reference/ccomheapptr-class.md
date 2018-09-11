---
title: Класс CComHeapPtr | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs:
- C++
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7a5b30ca507387b1529c9e9726e48735c844fac
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764833"
---
# <a name="ccomheapptr-class"></a>Класс CComHeapPtr

Класс смарт-указатель для управления кучей указателей.

## <a name="syntax"></a>Синтаксис

```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>Параметры

*T*  
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

*pData*  
Существующий объект `CComHeapPtr`.

### <a name="remarks"></a>Примечания

Указатель кучи при необходимости могут создаваться с помощью существующего `CComHeapPtr` объекта. Если Да, новый `CComHeapPtr` объект несет ответственность за управление новый указатель и ресурсы.

## <a name="see-also"></a>См. также

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
[Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)   
[Класс CComAllocator](../../atl/reference/ccomallocator-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
