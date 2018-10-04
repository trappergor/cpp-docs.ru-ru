---
title: Isbaseofstrict-структура | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fc41bdccf9cce3d455d4effd3541731929e5de2
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789271"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Параметры

*Base*<br/>
Базовый тип.

*Производные*<br/>
Производный тип.

## <a name="remarks"></a>Примечания

Проверяет, является ли один тип базовым для другого.

Первый шаблон проверяет, является ли тип, производный от базового типа, который может дать `true` или `false`. Второй шаблон проверяет, является ли тип является производным от самого себя, которая всегда создает `false`.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

name                            | Описание
------------------------------- | --------------------------------------------------
[IsBaseOfStrict::value](#value) | Указывает, является ли один тип базовым для другого.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IsBaseOfStrict`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="value"></a>IsBaseOfStrict::value

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Примечания

Указывает, является ли один тип базовым для другого.

Значение параметра `value` равно `true`, если тип `Base` является базовым классом типа `Derived`; в противном случае — значение `false`.
