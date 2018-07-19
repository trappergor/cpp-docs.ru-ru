---
title: Класс CInterfaceArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c33e0783acfba1b460894ac8f5dde80e61780762
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882726"
---
# <a name="cinterfacearray-class"></a>Класс CInterfaceArray
Этот класс предоставляет методы, используемые при создании массива указателей COM-интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Параметры  
 *I*  
 COM-интерфейс, указав тип указателя для сохранения.  
  
 *piid*  
 Указатель на идентификатор IID *я*.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Конструктор для интерфейса массива.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и производные методы для создания массива указателей интерфейса СОМ. Используйте [CInterfaceList](../../atl/reference/cinterfacelist-class.md) когда необходима списка.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cinterfacearray"></a>  CInterfaceArray::CInterfaceArray  
 Конструктор.  
  
```
CInterfaceArray() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует этот массив смарт-указатель.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlArray](../../atl/reference/catlarray-class.md)   
 [Класс CComQIPtr](../../atl/reference/ccomqiptr-class.md)   
 [Класс CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
