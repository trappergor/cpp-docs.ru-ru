---
title: Isbaseofstrict-структура | Документация Майкрософт
ms.custom: ''
ms.date: 09/21/2018
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
ms.openlocfilehash: 137f572f01d4aa72b9141c3ca172426fdb575b48
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169528"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename Base,
   typename Derived
>

struct IsBaseOfStrict;
template <
   typename Base
>
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
