---
title: Класс RemoveIUnknown | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd52dcdc5fed543d65311aaa7e8a61a9d2019b8a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020295"
---
# <a name="removeiunknown-class"></a>Класс RemoveIUnknown
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс.  
  
## <a name="remarks"></a>Примечания  
 Создает тип, эквивалентный базовому типу `IUnknown`, но имеющий невиртуальные функции-члены `QueryInterface`, `AddRef` и `Release`.  
  
 По умолчанию методы модели COM предоставляют виртуальные `QueryInterface`, `AddRef`, и `Release` методы. Однако для `ComPtr` не требуется нагрузка, связанная с виртуальными методами. Интерфейс `RemoveIUnknown` исключает эту нагрузку, предоставляя закрытые невиртуальные методы `QueryInterface`, `AddRef` и `Release`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`ReturnType`|Синоним для типа, которое эквивалентно значению параметра-шаблона *T* , но имеющий невиртуальные `IUnknown` членов.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `T`  
  
 `RemoveIUnknown`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)