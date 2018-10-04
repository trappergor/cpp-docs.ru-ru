---
title: объект (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14bb20cae26ecb012362b65f86aae5e422170a1a
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791287"
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

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[Custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)  