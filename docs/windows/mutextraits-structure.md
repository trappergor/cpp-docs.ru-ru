---
title: Mutextraits-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs:
- C++
helpviewer_keywords:
- MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: deebac1516724469882391c3c856a9ed7a588c88
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018982"
---
# <a name="mutextraits-structure"></a>MutexTraits - структура
Определяет общие характеристики [мьютекс](../windows/mutex-class1.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
struct MutexTraits : HANDLENullTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод MutexTraits::Unlock](../windows/mutextraits-unlock-method.md)|Освобождает управлением общего ресурса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)