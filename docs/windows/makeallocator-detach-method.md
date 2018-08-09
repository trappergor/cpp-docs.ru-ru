---
title: Метод MakeAllocator::Detach | Документация Майкрософт
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
ms.openlocfilehash: b629ec70ed29866d0f8e37d9e6ce746fbfe6f117
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018469"
---
# <a name="makeallocatordetach-method"></a>Метод MakeAllocator::Detach
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
__forceinline void Detach();  
```  
  
## <a name="remarks"></a>Примечания  
 Отменяет связь памяти, выделенной с помощью [выделения](../windows/makeallocator-allocate-method.md) метод из текущего **MakeAllocator** объекта.  
  
 При вызове метода **Detach()**, вы несете ответственность за удаление памяти, предоставляемые `Allocate` метод.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Makeallocator-класс](../windows/makeallocator-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)