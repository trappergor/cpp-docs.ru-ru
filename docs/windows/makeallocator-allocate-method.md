---
title: Метод MakeAllocator::Allocate | Документация Майкрософт
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
ms.openlocfilehash: 4422dea0b0bfb07904d0c4defad8f33281a51bec
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609866"
---
# <a name="makeallocatorallocate-method"></a>Метод MakeAllocator::Allocate

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
__forceinline void* Allocate();
```

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении указатель на выделенную память; в противном случае **nullptr**.

## <a name="remarks"></a>Примечания

Выделяет память и связывает его с текущим **MakeAllocator** объекта.

Размер выделенной памяти равен размеру типа, указанного текущим **MakeAllocator** параметр шаблона.

Разработчику необходимо переопределить только **Allocate()** метод для реализации другой модели выделения памяти.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс MakeAllocator](../windows/makeallocator-class.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)