---
title: DontUseNewUseMake - класс
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: f38833fa851030735dca34f16be9eaa9eb52069a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466759"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Примечания

Предотвращает использование оператора `new` в `RuntimeClass`. Следовательно, необходимо использовать [функция](../windows/make-function.md) вместо этого.

## <a name="members"></a>Участники

### <a name="public-operators"></a>Открытые операторы

Имя                                             | Описание
------------------------------------------------ | ---------------------------------------------------------------------------
[Новый DontUseNewUseMake::operator](#operator-new) | Перегружает оператор `new` и предотвращает использование в `RuntimeClass`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DontUseNewUseMake`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="operator-new"></a>Новый DontUseNewUseMake::operator

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Параметры

*__unnamed0*<br/>
Неименованный параметр, который определяет количество байт памяти для выделения.

*Размещение*<br/>
Выделяемый тип.

### <a name="return-value"></a>Возвращаемое значение

Предоставляет способ передачи дополнительных аргументов при перегрузке оператора `new`.

### <a name="remarks"></a>Примечания

Перегружает оператор `new` и предотвращает использование в `RuntimeClass`.
