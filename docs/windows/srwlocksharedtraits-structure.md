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
ms.openlocfilehash: c606a1a7d32a02442e767a31543a76a4dccf295e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652478"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits - структура
Описывает общие характеристики `SRWLock` класс в режим разделяемой блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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