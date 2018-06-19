---
title: Константа ArgTraits::args | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits::args
dev_langs:
- C++
helpviewer_keywords:
- args constant
ms.assetid: a68100ab-254b-4571-a0bc-946f1633a46b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f87b29634d5b9acef2e2ccb3f7b4d5f227433d38
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855777"
---
# <a name="argtraitsargs-constant"></a>Константа ArgTraits::args
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int args = -1; ;  
```  
  
## <a name="remarks"></a>Примечания  
 Содержит счетчик количества параметров метода Invoke для интерфейса делегата.  
  
## <a name="remarks"></a>Примечания  
 Когда `args` равно -1 указывает, может быть не соответствует сигнатуре метода Invoke.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [ArgTraits-структура](../windows/argtraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)