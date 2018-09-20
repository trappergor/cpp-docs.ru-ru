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
ms.openlocfilehash: ab0219c8893ff7ad35e29f9dd8b18be18caf8eb9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378128"
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

*Элемент*<br/>
Указатель на обработчик событий для добавления.

## <a name="remarks"></a>Примечания

Добавляет указанный обработчик событий в конец внутреннего массива из обработчиков событий.

**AddTail()** предназначен для использования в среде только `EventSource` класса.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс EventTargetArray](../windows/eventtargetarray-class.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)