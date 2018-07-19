---
title: Класс CAutoPtrArray | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b99fe8fde475453c9e6dc0b524a6b1b94821bf75
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358955"
---
# <a name="cautoptrarray-class"></a>Класс CAutoPtrArray
Этот класс предоставляет методы, используемые при создании массива интеллектуальных указателей.  
  
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
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и наследует методы из [CAtlArray](../../atl/reference/catlarray-class.md) и [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) для упрощения создания объекта класса коллекции, хранение интеллектуальные указатели.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cautoptrarray"></a>  CAutoPtrArray::CAutoPtrArray  
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
