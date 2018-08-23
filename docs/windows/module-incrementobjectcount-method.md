---
title: Метод Module::IncrementObjectCount | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::IncrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- IncrementObjectCount method
ms.assetid: 268b79be-15c3-4b07-884e-18da2c7281f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c5b1b50b096bf7fcda2aa26bf3e2b7820499267
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599429"
---
# <a name="moduleincrementobjectcount-method"></a>Метод Module::IncrementObjectCount

Увеличивает число объектов, отслеживаемых модулем.

## <a name="syntax"></a>Синтаксис

```cpp
virtual long IncrementObjectCount();
```

## <a name="return-value"></a>Возвращаемое значение

Счетчик перед выполнением операции инкремента.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)