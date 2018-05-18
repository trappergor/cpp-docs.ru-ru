---
title: Структура SRWLockExclusiveTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b5d56c4e0c31b56e5bdc92a9d209b58cd15ffb1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits - структура
Описывает общие характеристики класса SRWLock в режиме эксклюзивной блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`Type`|Синоним для типа указателя [SRWLOCK](../windows/srwlock-class.md) класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод SRWLockExclusiveTraits::GetInvalidValue](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Извлекает объект SRWLockExclusiveTraits, всегда является недопустимым.|  
|[Метод SRWLockExclusiveTraits::Unlock](../windows/srwlockexclusivetraits-unlock-method.md)|Освобождает исключительный контроль указанного объекта SRWLock.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)