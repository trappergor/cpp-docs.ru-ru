---
title: "Класс CAutoPtrArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 58ee329c7a3925fe3a29cf9738670cfa71df6777
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptrarray-class"></a>Класс CAutoPtrArray
Этот класс предоставляет методы, используемые при создании массива интеллектуальные указатели.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Параметры  
 `E`  
 Тип указателя.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и производным методов из [CAtlArray](../../atl/reference/catlarray-class.md) и [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) для упрощения создания объекта класса коллекции, хранение интеллектуальные указатели.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray  
 Конструктор.  
  
```
CAutoPtrArray() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует массив интеллектуального указателя.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlArray](../../atl/reference/catlarray-class.md)   
 [Класс CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)   
 [Класс CAutoPtrList](../../atl/reference/cautoptrlist-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

