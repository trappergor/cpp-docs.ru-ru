---
title: Константа ArgTraitsHelper::args | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
dev_langs:
- C++
helpviewer_keywords:
- args constant
ms.assetid: 1c0efa32-c072-43e3-bbd9-a3f6aec069a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49ee69015837d27f7445db9f765739fc1d28152c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642878"
---
# <a name="argtraitshelperargs-constant"></a>Константа ArgTraitsHelper::args
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
static const int args = Traits::args;  
```  
  
## <a name="remarks"></a>Примечания  
 Помогает [ArgTraitsHelper::args](../windows/argtraitshelper-args-constant.md) следить счетчик числа параметров `Invoke` метод для интерфейса делегата.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Argtraitshelper-структура](../windows/argtraitshelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)