---
title: Пространство имен default
ms.date: 12/30/2016
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
ms.openlocfilehash: ffea9e1132b4c66f38661392cbafb94635b318e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558730"
---
# <a name="default-namespace"></a>Пространство имен default

`default` Пространство имен области встроенные типы, которые поддерживаются в C + +/ CX.

## <a name="syntax"></a>Синтаксис

```
namespace default;
```

### <a name="members"></a>Участники

Все встроенные типы наследуют следующие члены.

|||
|-|-|
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|Определяет, равен ли заданный объект текущему объекту.|
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Возвращает хэш-код данного экземпляра.|
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|Возвращает строку, которая представляет текущий тип.|
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|Возвращает строку, которая представляет текущий тип.|

### <a name="built-in-types"></a>Встроенные типы

|name|Описание|
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

## <a name="see-also"></a>См. также

[Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)