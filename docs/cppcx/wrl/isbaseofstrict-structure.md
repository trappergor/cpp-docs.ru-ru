---
title: IsBaseOfStrict - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: 71db5a1b52a7d7d5471c15591fb34d954b465d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371352"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Параметры

*Базы*<br/>
Базовый тип.

*Производным*<br/>
Производный тип.

## <a name="remarks"></a>Remarks

Проверяет, является ли один тип базовым для другого.

Первый шаблон проверяет, является ли тип выведен из базового типа, который может дать **истинное** или **ложное.** Второй шаблон проверяет, является ли тип производным от самого себя, что всегда дает **ложное.**

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

Имя                            | Описание
------------------------------- | --------------------------------------------------
[IsBaseOfStrict::стоимость](#value) | Указывает, является ли один тип базовым для другого.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IsBaseOfStrict`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="isbaseofstrictvalue"></a><a name="value"></a>IsBaseOfStrict::стоимость

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Remarks

Указывает, является ли один тип базовым для другого.

`value`**верно,** если `Base` тип является базовым `Derived`классом типа, в противном случае это **ложно.**
