---
title: "Класс CHeapPtrList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CHeapPtrList
- CHeapPtrList
- ATL.CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 9acf18d0e0a72f27a335cefca81341c95d530ae5
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrlist-class"></a>Класс CHeapPtrList
Этот класс предоставляет методы, используемые при создании список указателей кучи.  
  
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
 `E`  
 Тип объекта для сохранения в класс коллекции.  
  
 `Allocator`  
 Класс выделения памяти для использования. Значение по умолчанию — [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и производным методов из [CAtlList](../../atl/reference/catllist-class.md) и [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) для упрощения создания объекта класса коллекции хранения указателей кучи.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="a-namecheapptrlista--cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a>CHeapPtrList::CHeapPtrList  
 Конструктор.  
  
```
CHeapPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Размер блока.  
  
### <a name="remarks"></a>Примечания  
 Размер блока измеряется объем памяти, выделяемый при новый элемент является обязательным. Размер блока снизить вызовы процедур выделения памяти, но использует больше ресурсов.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlList](../../atl/reference/catllist-class.md)   
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

