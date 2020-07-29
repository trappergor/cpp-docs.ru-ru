---
title: no_injected_text (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 7e5c822c45888f41e8dd849f25658d0139e6fda0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87201249"
---
# <a name="no_injected_text"></a>no_injected_text

Не позволяет компилятору внедрять код в результате использования атрибута.

## <a name="syntax"></a>Синтаксис

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Параметры

*boolean*<br/>
(Необязательно) **`true`** Если вы не хотите внедрять код, **`false`** чтобы разрешить внедрение кода. **`true`** значение по умолчанию —.

## <a name="remarks"></a>Remarks

Наиболее распространенным применением атрибута **no_injected_text** C++ является параметр компилятора [/FX](../../build/reference/fx-merge-injected-code.md) , который вставляет атрибут **no_injected_text** в MRG-файл.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|В любом месте|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)
