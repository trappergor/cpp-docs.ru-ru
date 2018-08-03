---
title: Метод CriticalSectionTraits::Unlock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f66f185692c200ea459b88363143c0cc1af9d55
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466014"
---
# <a name="criticalsectiontraitsunlock-method"></a>Метод CriticalSectionTraits::Unlock
Специализирует шаблон CriticalSection так, чтобы она поддерживала снятию владения объектом указанного критический раздел.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *cs*  
 Указатель на объект критической секции.  
  
## <a name="remarks"></a>Примечания  
 *Тип* модификатор определяется как `typedef CRITICAL_SECTION* Type;`.  
  
 Дополнительные сведения см. в разделе «LeaveCriticalSection function» в разделе «Функции синхронизации» в документации по Windows API.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)