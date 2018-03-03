---
title: "Структура InterfaceListHelper | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
dev_langs:
- C++
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 241613f94431903c7d9e3957cece46844dc67ad9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename T0,  
   typename T1 = Nil,  
   typename T2 = Nil,  
   typename T3 = Nil,  
   typename T4 = Nil,  
   typename T5 = Nil,  
   typename T6 = Nil,  
   typename T7 = Nil,  
   typename T8 = Nil,  
   typename T9 = Nil  
>  
struct InterfaceListHelper;  
  
template <  
   typename T0  
>  
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T0`  
 Параметр шаблона, 0, который является обязательным.  
  
 `T1`  
 Параметр шаблона, 1, который по умолчанию не определен.  
  
 `T2`  
 Параметр шаблона, 2, которая по умолчанию не определен. Третий параметр шаблона.  
  
 `T3`  
 Параметр шаблона, 3, которая по умолчанию не определен.  
  
 `T4`  
 Параметр шаблона, 4, который по умолчанию не определен.  
  
 `T5`  
 Параметр шаблона, 5, который по умолчанию не определен.  
  
 `T6`  
 Параметр шаблона, 6, которая по умолчанию не определен.  
  
 `T7`  
 Параметр шаблона, 7, который по умолчанию не определен.  
  
 `T8`  
 Параметр шаблона, 8, которая по умолчанию не определен.  
  
 `T9`  
 Параметр шаблона, 9, который по умолчанию не определен.  
  
## <a name="remarks"></a>Примечания  
 Мы добавим тип InterfaceList рекурсивного применения аргументов параметра указанного шаблона.  
  
 Параметр шаблона используется шаблон InterfaceListHelper `T0` для определения данных, первый элемент в InterfaceList-структура, а затем рекурсивно применяет шаблон InterfaceListHelper остальные параметры шаблона. InterfaceListHelper прекращается, когда нет оставшихся параметров шаблона.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`TypeT`|Синоним для типа InterfaceList.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `InterfaceListHelper`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)