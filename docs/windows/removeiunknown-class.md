---
title: "Класс RemoveIUnknown | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b62362004f0528b16ef3dac7cbe601b8b85ce3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="removeiunknown-class"></a>Класс RemoveIUnknown
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс.  
  
## <a name="remarks"></a>Примечания  
 Создает тип, эквивалентный базовому типу `IUnknown`, но имеющий невиртуальные функции-члены `QueryInterface`, `AddRef` и `Release`.  
  
 По умолчанию методы модели COM предоставляют виртуальные методы `QueryInterface`, `AddRef` и Release. Однако для `ComPtr` не требуется нагрузка, связанная с виртуальными методами. Интерфейс `RemoveIUnknown` исключает эту нагрузку, предоставляя закрытые невиртуальные методы `QueryInterface`, `AddRef` и `Release`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`ReturnType`|Синоним для типа, эквивалентного параметру шаблона `T`, но имеющего невиртуальные члены IUnknown.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `T`  
  
 `RemoveIUnknown`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)