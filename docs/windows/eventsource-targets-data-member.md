---
title: Элемент данных Eventsource::targets_ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::targets_
dev_langs:
- C++
helpviewer_keywords:
- targets_ data member
ms.assetid: 5d5cee05-3315-4514-bce2-19173c923c7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fcdcb759c90009410f76a4b10039a0d976ca0cc4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605119"
---
# <a name="eventsourcetargets-data-member"></a>Элемент данных EventSource::targets_

Массив из одного или нескольких обработчиков событий.

## <a name="syntax"></a>Синтаксис

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

## <a name="remarks"></a>Примечания

Когда события, представленного текущим **EventSource** объект встречается, обработчики событий вызываются.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также
[Класс EventSource](../windows/eventsource-class.md)