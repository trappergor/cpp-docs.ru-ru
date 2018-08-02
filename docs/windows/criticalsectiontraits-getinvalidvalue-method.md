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
ms.openlocfilehash: cf0d52769052a36c0b494d19204dd6c07f0b2404
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463389"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>Метод CriticalSectionTraits::GetInvalidValue
Специализируется **CriticalSection** шаблона, чтобы шаблон всегда является недопустимым.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает указатель на недопустимую критическую секцию.  
  
## <a name="remarks"></a>Примечания  
 *Тип* модификатор определяется как `typedef CRITICAL_SECTION* Type;`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)