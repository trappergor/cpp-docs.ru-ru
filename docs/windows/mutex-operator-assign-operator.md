---
title: Mutex::operator =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea5aee6f248487097462028a763a98b4e814a17a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396796"
---
# <a name="mutexoperator-operator"></a>Оператор Mutex::operator=

Назначает (перемещается) указанного **мьютекс** объект с текущим **мьютекс** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на **мьютекс** объекта.

## <a name="return-value"></a>Возвращаемое значение

Ссылку на текущий **мьютекс** объекта.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе **семантику перемещения** раздел [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс Mutex](../windows/mutex-class1.md)