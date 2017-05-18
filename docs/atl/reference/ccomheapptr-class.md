---
title: "Класс CComHeapPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 0e5196a98b8fd76b2e7e791fd2cd9549099a1cc9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheapptr-class"></a>Класс CComHeapPtr
Класс интеллектуального указателя для управления кучей указателей.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта, который должен храниться в куче.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 `CComHeapPtr`является производным от `CHeapPtr`, но использует [CComAllocator](../../atl/reference/ccomallocator-class.md) для выделения памяти с помощью COM-подпрограммы. В разделе [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) для доступные методы.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr  
 Конструктор.  
  
```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pData`  
 Существующий объект `CComHeapPtr`.  
  
### <a name="remarks"></a>Примечания  
 Указатель кучи при необходимости могут создаваться с помощью существующего `CComHeapPtr` объекта. В этом случае новый `CComHeapPtr` объект несет ответственность за управление новый указатель и ресурсы.  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)   
 [Класс CComAllocator](../../atl/reference/ccomallocator-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

