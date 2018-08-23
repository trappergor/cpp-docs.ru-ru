---
title: объект (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: e8d69ccb0b5a0c0f0dd13d377841732d9f663e91
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607589"
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

См. в разделе [недоступная для просмотра](../windows/nonbrowsable.md) пример демонстрирует использование **объект**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[dual](../windows/dual.md)  
[dispinterface](../windows/dispinterface.md)  
[Custom](../windows/custom-cpp.md)  
[__interface](../cpp/interface.md)  