---
title: Метод MakeAllocator::Allocate | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs:
- C++
helpviewer_keywords:
- Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0e8d387dea7687ad61d85f975d58aa47489266d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876220"
---
# <a name="makeallocatorallocate-method"></a>Метод MakeAllocator::Allocate
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если операция завершилась успешно, представляет указатель на выделенную память; в противном случае — значение `nullptr`.  
  
## <a name="remarks"></a>Примечания  
 Выделяет память и связывает ее с текущим объектом MakeAllocator.  
  
 Размер выделенной памяти равен размеру типа, заданного текущим параметром шаблона MakeAllocator.  
  
 Разработчику необходимо переопределить только метод Allocate() для реализации другой модели выделения памяти.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [MakeAllocator-класс](../windows/makeallocator-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)