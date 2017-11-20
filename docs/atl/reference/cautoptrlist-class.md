---
title: "Класс CAutoPtrList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
dev_langs: C++
helpviewer_keywords: CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 79ca570b8f4534287ae4ec40167de3bc3d947139
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cautoptrlist-class"></a>Класс CAutoPtrList
Этот класс предоставляет методы, используемые при построении списка интеллектуальных указателей.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename E>  
class CAutoPtrList : 
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Параметры  
 `E`  
 Тип указателя.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и наследует методы из [CAtlList](../../atl/reference/catllist-class.md) и [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) для упрощения создания списка объектов хранения интеллектуальные указатели. Класс [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) предоставляет аналогичные функции для объекта array.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CAutoPtrList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cautoptrlist"></a>CAutoPtrList::CAutoPtrList  
 Конструктор.  
  
```
CAutoPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Размер блока по умолчанию 10.  
  
### <a name="remarks"></a>Примечания  
 Размер блока — это мера, объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlList](../../atl/reference/catllist-class.md)   
 [Класс CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
