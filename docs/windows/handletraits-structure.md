---
title: Handletraits-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
dev_langs:
- C++
helpviewer_keywords:
- HANDLETraits structure
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2193743da9e7b5667714650660cd8e1efdb5cf4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610985"
---
# <a name="handletraits-structure"></a>HANDLETraits - структура

Определяет общие характеристики дескриптора.

## <a name="syntax"></a>Синтаксис

```cpp
struct HANDLETraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`Type`|Синоним для HANDLE.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод HANDLETraits::Close](../windows/handletraits-close-method.md)|Закрывает указанный дескриптор.|
|[Метод HANDLETraits::GetInvalidValue](../windows/handletraits-getinvalidvalue-method.md)|Представляет недопустимый дескриптор.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLETraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)