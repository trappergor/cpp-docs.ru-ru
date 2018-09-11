---
title: Метод EventTargetArray::Begin | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::Begin
dev_langs:
- C++
helpviewer_keywords:
- Begin method
ms.assetid: 1cc7fdfd-a2c4-4b28-93cf-1c82842294ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 738ee52eb68cfbb03a380ffac52efdb4010b5205
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602135"
---
# <a name="eventtargetarraybegin-method"></a>Метод EventTargetArray::Begin

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
ComPtr<IUnknown>* Begin();
```

## <a name="return-value"></a>Возвращаемое значение

Адрес первого элемента во внутреннем массиве обработчиков событий.

## <a name="remarks"></a>Примечания

Получает адрес первого элемента во внутреннем массиве обработчиков событий.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс EventTargetArray](../windows/eventtargetarray-class.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)