---
title: Структура SRWLockSharedTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a18edef3fa658608459244143a5e48738f0c3a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits - структура
Описывает общие характеристики класса SRWLock в режиме общего доступа блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`Type`|Синоним для типа указателя [SRWLOCK](../windows/srwlock-class.md) класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод SRWLockSharedTraits::GetInvalidValue](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Извлекает объект SRWLockSharedTraits, всегда является недопустимым.|  
|[Метод SRWLockSharedTraits::Unlock](../windows/srwlocksharedtraits-unlock-method.md)|Освобождает исключительный контроль указанного объекта SRWLock.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)