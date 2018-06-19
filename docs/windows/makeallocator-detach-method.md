---
title: Метод MakeAllocator::Detach | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: 78012634-2dda-4ea2-9ffe-40f105d2fe47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50afca04492c29aa526f7a004c6e0f725022e9ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876973"
---
# <a name="makeallocatordetach-method"></a>Метод MakeAllocator::Detach
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline void Detach();  
```  
  
## <a name="remarks"></a>Примечания  
 Отсоединяет памяти, выделенной с помощью [Allocate](../windows/makeallocator-allocate-method.md) метод с текущим объектом MakeAllocator.  
  
 Если вызвать Detach(), вы отвечаете за удаление памяти, предоставляемый методом распределения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [MakeAllocator-класс](../windows/makeallocator-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)