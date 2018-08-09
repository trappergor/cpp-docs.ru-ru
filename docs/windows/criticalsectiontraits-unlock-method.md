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
ms.openlocfilehash: b64f44e2188848a25e607c53171e25aa721e9bc4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641370"
---
# <a name="criticalsectiontraitsunlock-method"></a>Метод CriticalSectionTraits::Unlock
Специализируется `CriticalSection` шаблона, так что он поддерживает снятию владения объектом указанного критический раздел.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *cs*  
 Указатель на объект критической секции.  
  
## <a name="remarks"></a>Примечания  
 Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.  
  
 Дополнительные сведения см. в разделе **функция LeaveCriticalSection** в **функций синхронизации** раздел документации Windows API.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)