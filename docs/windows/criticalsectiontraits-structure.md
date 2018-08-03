---
title: Criticalsectiontraits-структура | Документация Майкрософт
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
ms.openlocfilehash: 8b10d130190308520771e37e97d34238f75670ad
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466687"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits - структура
Специализируется объект CriticalSection для поддержки недопустимую критическую секцию или функцию для освобождения критического раздела.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`Type`|Объект **typedef** указатель, определяющий критической секции. `Type` определяется как `typedef CRITICAL_SECTION* Type;`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод CriticalSectionTraits::GetInvalidValue](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Специализируется `CriticalSection` шаблона, чтобы шаблон всегда является недопустимым.|  
|[Метод CriticalSectionTraits::Unlock](../windows/criticalsectiontraits-unlock-method.md)|Специализируется `CriticalSection` шаблона, так что он поддерживает снятию владения объектом указанного критический раздел.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)