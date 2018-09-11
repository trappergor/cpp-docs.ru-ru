---
title: Метод Module::GetObjectCount | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetObjectCount
dev_langs:
- C++
helpviewer_keywords:
- GetObjectCount method
ms.assetid: 9fe29747-7e7f-40f2-9f6b-9a206b17fa8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2be87f336adeb156789bb8c0ae7c8d05c8de39a4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608641"
---
# <a name="modulegetobjectcount-method"></a>Метод Module::GetObjectCount

Извлекает количество объектов, управляемых этим модулем.

## <a name="syntax"></a>Синтаксис

```cpp
virtual long GetObjectCount() const;
```

## <a name="return-value"></a>Возвращаемое значение

Текущее количество объектов, управляемых этим модулем.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)