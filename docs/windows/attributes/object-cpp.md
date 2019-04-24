---
title: объект (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: c0f544e84e5110761dfd01e25abef4352f055ff5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022363"
---
# <a name="object-c"></a>object (C++)

Определяет пользовательский интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
[object]
```

## <a name="remarks"></a>Примечания

Когда перед определение интерфейса **объект** атрибут C++ вызывает интерфейс помещается в IDL-файл как пользовательский интерфейс.

Любой интерфейс, отмеченный атрибутом объект должен наследовать от `IUnknown`. Это условие выполняется в том случае, если любой из этих базовых интерфейсов наследуют от `IUnknown`. Если нет базовых интерфейсов наследуют от `IUnknown`, компилятор вызовет интерфейс, отмеченный атрибутом **объект** для наследования от `IUnknown`.

## <a name="example"></a>Пример

См. в разделе [недоступная для просмотра](nonbrowsable.md) пример демонстрирует использование **объект**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)