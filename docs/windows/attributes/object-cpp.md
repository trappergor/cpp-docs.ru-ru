---
title: Object (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: 4545d899c13a1eabf8ea5fb6fe3918fb5f05b626
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214702"
---
# <a name="object-c"></a>object (C++)

Определяет пользовательский интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
[object]
```

## <a name="remarks"></a>Remarks

Если перед определением интерфейса, атрибут **объекта** C++ помещает интерфейс в IDL-файл как пользовательский интерфейс.

Любой интерфейс, помеченный объектом, должен наследовать от `IUnknown`. Это условие выполняется, если какой-либо из базовых интерфейсов наследует от `IUnknown`. Если базовые интерфейсы не наследуются от `IUnknown`, компилятор приведет к тому, что интерфейс, помеченный **объектом** , будет производным от `IUnknown`.

## <a name="example"></a>Пример

См. Пример использования **объекта**в [неотображаемом](nonbrowsable.md) виде.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
