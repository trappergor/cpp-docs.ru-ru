---
title: Класс CComHeapPtr | Документы Microsoft
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
ms.openlocfilehash: 1937bb96cabfd1a42650e2a27fd04c11aa648f2b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359062"
---
# <a name="ccomheapptr-class"></a>Класс CComHeapPtr
Класс интеллектуальный указатель для управления указатели кучи.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта для сохранения в куче.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 `CComHeapPtr` является производным от `CHeapPtr`, но использует [CComAllocator](../../atl/reference/ccomallocator-class.md) для выделения памяти с помощью COM-подпрограммы. В разделе [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) для доступных методов.  
  
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
 `pData`  
 Существующий объект `CComHeapPtr`.  
  
### <a name="remarks"></a>Примечания  
 Указатель кучи при необходимости могут создаваться с помощью существующей `CComHeapPtr` объекта. В этом случае новый `CComHeapPtr` объект несет ответственность за управление новый указатель и ресурсы.  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)   
 [Класс CComAllocator](../../atl/reference/ccomallocator-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
