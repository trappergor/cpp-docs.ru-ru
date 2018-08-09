---
title: Метод CriticalSectionTraits::GetInvalidValue | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 01efd9bf3941a5b19e1f0fe6c106d47f1b6e9fcf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642065"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>Метод CriticalSectionTraits::GetInvalidValue
Специализируется **CriticalSection** шаблона, чтобы шаблон всегда является недопустимым.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает указатель на недопустимую критическую секцию.  
  
## <a name="remarks"></a>Примечания  
 Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)