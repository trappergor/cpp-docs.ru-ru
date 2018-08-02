---
title: Константа ArgTraits::args | Документация Майкрософт
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
ms.openlocfilehash: b6f0059d167b04c9a4b177d1851ad88133ef5cd3
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466560"
---
# <a name="argtraitsargs-constant"></a>Константа ArgTraits::args
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int args = -1; ;  
```  
  
## <a name="remarks"></a>Примечания  
 Ведет статистику, число параметров `Invoke` метод для интерфейса делегата.  
  
## <a name="remarks"></a>Примечания  
 Когда `args` равно -1 указывает, может существовать совпадения `Invoke` сигнатуру метода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Argtraits-структура](../windows/argtraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)