---
title: Метод EventTargetArray::Length | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::Length
dev_langs:
- C++
helpviewer_keywords:
- Length method
ms.assetid: f8bd8d42-977b-4695-b07a-227a68be5259
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a23945ae4489ace4d2017d9418f719da0849f95
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400280"
---
# <a name="eventtargetarraylength-method"></a>Метод EventTargetArray::Length

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
size_t Length();
```

## <a name="return-value"></a>Возвращаемое значение

Текущее количество элементов в массиве внутренних обработчиков событий.

## <a name="remarks"></a>Примечания

Получает текущее число элементов в массиве внутренних обработчиков событий.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс EventTargetArray](../windows/eventtargetarray-class.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)