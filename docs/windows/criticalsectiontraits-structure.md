---
title: Структура CriticalSectionTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5534173d594b8fc09ceca8ec44a1c1223bc550b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits - структура
Специализирует объект CriticalSection для поддержки недопустимую критическую секцию или функцию освобождения критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`Type`|Объект `typedef` , определяющий указатель для критической секции. `Type` определяется как `typedef CRITICAL_SECTION* Type;`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод CriticalSectionTraits::GetInvalidValue](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Специализирует шаблон CriticalSection таким образом, что он всегда будет являться недопустимым.|  
|[Метод CriticalSectionTraits::Unlock](../windows/criticalsectiontraits-unlock-method.md)|Специализирует шаблон CriticalSection так, чтобы она поддерживала снимать владения объектом указанного критической секции.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)