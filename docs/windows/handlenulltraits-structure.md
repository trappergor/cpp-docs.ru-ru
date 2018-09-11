---
title: Handlenulltraits-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
dev_langs:
- C++
helpviewer_keywords:
- HANDLENullTraits structure
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3a49a1a1ac4495c7697fc041f8fcf217850f09d8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609428"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits - структура

Определяет общие характеристики дескриптора неинициализированным.

## <a name="syntax"></a>Синтаксис

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`Type`|Синоним для HANDLE.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод HANDLENullTraits::Close](../windows/handlenulltraits-close-method.md)|Закрывает указанный дескриптор.|
|[Метод HANDLENullTraits::GetInvalidValue](../windows/handlenulltraits-getinvalidvalue-method.md)|Представляет недопустимый дескриптор.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLENullTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)