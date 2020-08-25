---
title: Пространство имен default
ms.date: 12/30/2016
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
ms.openlocfilehash: 5696730bcef08ad11be4a2b689e95eb3c13e11eb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845709"
---
# <a name="default-namespace"></a>Пространство имен default

`default`Пространство имен — это встроенные типы, поддерживаемые C++/CX.

## <a name="syntax"></a>Синтаксис

```
namespace default;
```

### <a name="members"></a>Участники

Все встроенные типы наследуют следующие члены.

| Имя | Описание |
|--|--|
| [default::(имя_типа)::Equals](../cppcx/default-type-name-equals-method.md) | Определяет, равен ли указанный объект текущему объекту. |
| [default::(имя_типа)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md) | Возвращает хэш-код данного экземпляра. |
| [default::(имя_типа)::GetType](../cppcx/default-type-name-gettype-method.md) | Возвращает строку, которая представляет текущий тип. |
| [default::(имя_типа)::ToString](../cppcx/default-type-name-tostring-method.md) | Возвращает строку, которая представляет текущий тип. |

### <a name="built-in-types"></a>Встроенные типы

|Имя|Описание|
|----------|-----------------|
|`char16`|16-битовое нечисловое значение, представляющее кодовую точку Юникода (UTF-16).|
|`float32`|32-битовое число с плавающей запятой стандарта IEEE 754.|
|`float64`|64-битовое число с плавающей запятой стандарта IEEE 754.|
|`int16`|16-разрядное знаковое целое число.|
|`int32`|32-разрядное знаковое целое число.|
|`int64`|64-разрядное целое число со знаком.|
|`int8`|8-разрядное числовое значение со знаком.|
|`uint16`|16-разрядное целое число без знака.|
|`uint32`|32-разрядное целое число без знака.|
|`uint64`|64-разрядное целое число без знака.|
|`uint8`|8-разрядное числовое значение без знака.|

### <a name="requirements"></a>Требования

**Заголовок:** vccorlib.h

## <a name="see-also"></a>См. также раздел

[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)
