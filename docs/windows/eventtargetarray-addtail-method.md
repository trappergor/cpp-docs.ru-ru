---
title: Метод EventTargetArray::AddTail | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6609bba6d7adbddda152007e4db45c82f8039bc0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603682"
---
# <a name="eventtargetarrayaddtail-method"></a>Метод EventTargetArray::AddTail

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Параметры

*Элемент*  
Указатель на обработчик событий для добавления.

## <a name="remarks"></a>Примечания

Добавляет указанный обработчик событий в конец внутреннего массива из обработчиков событий.

**AddTail()** предназначен для использования в среде только `EventSource` класса.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс EventTargetArray](../windows/eventtargetarray-class.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)