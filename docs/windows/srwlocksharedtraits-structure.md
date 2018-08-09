---
title: Srwlocksharedtraits-структура | Документация Майкрософт
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
ms.openlocfilehash: db9a16671be21b2df7a4ce4f9d87a8b66e097e33
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020152"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits - структура
Описывает общие характеристики `SRWLock` класс в режим разделяемой блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`Type`|Синоним для указателя на [SRWLOCK](../windows/srwlock-class.md) класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод SRWLockSharedTraits::GetInvalidValue](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Извлекает **SRWLockSharedTraits** объект, который всегда является недопустимым.|  
|[Метод SRWLockSharedTraits::Unlock](../windows/srwlocksharedtraits-unlock-method.md)|Освобождает управлением указанного `SRWLock` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)