---
title: "Класс CInterfaceList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs: C++
helpviewer_keywords: CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5bd8817b325ebb9a9d8899211416dcbecfcd3f79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cinterfacelist-class"></a>Класс CInterfaceList
Этот класс предоставляет методы, используемые при построении список указателей интерфейса СОМ.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Параметры  
 `I`  
 COM-интерфейс, указав тип указателя для сохранения.  
  
 `piid`  
 Указатель на IID `I`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Конструктор список интерфейсов.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и производные методы для создания списка указателей интерфейса СОМ. Используйте [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) когда массив является обязательным.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cinterfacelist"></a>CInterfaceList::CInterfaceList  
 Конструктор список интерфейсов.  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Размер блока по умолчанию 10.  
  
### <a name="remarks"></a>Примечания  
 Размер блока — это мера, объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlList](../../atl/reference/catllist-class.md)   
 [Класс CComQIPtr](../../atl/reference/ccomqiptr-class.md)   
 [Класс CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
