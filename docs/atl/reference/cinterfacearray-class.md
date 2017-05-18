---
title: "Класс CInterfaceArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: 18
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
ms.openlocfilehash: a2a99eb3cff4f2381d4c58e4d1a7aaa167e83896
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cinterfacearray-class"></a>Класс CInterfaceArray
Этот класс предоставляет методы, используемые при создании массива указателей интерфейса СОМ.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Параметры  
 `I`  
 COM-интерфейс, указав тип указателя для сохранения.  
  
 `piid`  
 Указатель на идентификатор IID `I`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Конструктор для интерфейса массива.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и производные методы для создания массива указателей интерфейса СОМ. Используйте [CInterfaceList](../../atl/reference/cinterfacelist-class.md) Если список является обязательным.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray  
 Конструктор.  
  
```
CInterfaceArray() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует массив интеллектуального указателя.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlArray](../../atl/reference/catlarray-class.md)   
 [Класс CComQIPtr](../../atl/reference/ccomqiptr-class.md)   
 [Класс CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

