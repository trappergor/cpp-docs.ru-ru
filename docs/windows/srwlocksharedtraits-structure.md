---
title: Srwlocksharedtraits-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50bcfc728a2f228e4fa8444fe41cc25c3ff449a2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602250"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits - структура

Описывает общие характеристики `SRWLock` класс в режим разделяемой блокировки.

## <a name="syntax"></a>Синтаксис

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`Type`|Синоним для указателя на [SRWLOCK](../windows/srwlock-class.md) класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод SRWLockSharedTraits::GetInvalidValue](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Извлекает **SRWLockSharedTraits** объект, который всегда является недопустимым.|
|[Метод SRWLockSharedTraits::Unlock](../windows/srwlocksharedtraits-unlock-method.md)|Освобождает управлением указанного `SRWLock` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLockSharedTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)