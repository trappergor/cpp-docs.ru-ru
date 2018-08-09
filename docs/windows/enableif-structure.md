---
title: Enableif-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
dev_langs:
- C++
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 014099ce3e9152d2402263baaa6d6b30607756ed
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644977"
---
# <a name="enableif-structure"></a>EnableIf - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
   bool b,  
   typename T = void  
>  
  
struct EnableIf;  
template <  
   typename T  
>  
struct EnableIf<true, T>;  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Тип.  
  
 *b*  
 Выражение типа Boolean.  
  
## <a name="remarks"></a>Примечания  
 Определяет данные-член типа, указанного в качестве второго параметра шаблона, если первый параметр шаблона, результатом которого является **true**.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`type`|Если параметр шаблона *b* принимает значение **true**, частичная специализация определяет данные-член `type` типа `T`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `EnableIf`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)