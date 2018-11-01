---
title: no_injected_text (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: af4bb4b07439c0a5dacfa0d4956db564d2dccefe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618122"
---
# <a name="noinjectedtext"></a>no_injected_text

Запрещает компилятору вставку кода в результате использования атрибута.

## <a name="syntax"></a>Синтаксис

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Параметры

*Логическое значение*<br/>
(Необязательно) **true** Если нет кода, подставленного, **false** чтобы кода, которые следует вставить. **значение true,** используется по умолчанию.

## <a name="remarks"></a>Примечания

Наиболее распространенное использование **no_injected_text** C++ атрибут должен быть, [/Fx](../../build/reference/fx-merge-injected-code.md) параметр компилятора, который вставляет **no_injected_text** атрибут в MRG-файла.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)