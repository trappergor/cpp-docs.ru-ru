---
title: Handletraits-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
dev_langs:
- C++
helpviewer_keywords:
- HANDLETraits structure
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f722745b1283f25bd284adb3b55dcb340d78f07
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649917"
---
# <a name="handletraits-structure"></a>HANDLETraits - структура
Определяет общие характеристики дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
struct HANDLETraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`Type`|Синоним для HANDLE.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод HANDLETraits::Close](../windows/handletraits-close-method.md)|Закрывает указанный дескриптор.|  
|[Метод HANDLETraits::GetInvalidValue](../windows/handletraits-getinvalidvalue-method.md)|Представляет недопустимый дескриптор.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HANDLETraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)