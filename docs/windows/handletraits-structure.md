---
title: Структура HANDLETraits | Документы Microsoft
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
ms.openlocfilehash: 1aae09030ff6cad518028833ce5d4f7b06300a69
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="handletraits-structure"></a>HANDLETraits - структура
Определяет общие характеристики дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct HANDLETraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`Type`|Синоним для HANDLE.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
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