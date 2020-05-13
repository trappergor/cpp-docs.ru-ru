---
title: no_injected_text (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 5f98be3478b2e1eeb4b464f1784f3f4ece22d8a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166618"
---
# <a name="no_injected_text"></a>no_injected_text

Не позволяет компилятору внедрять код в результате использования атрибута.

## <a name="syntax"></a>Синтаксис

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Параметры

*boolean*<br/>
Используемых **значение true** , если не нужно внедрять код, **значение false** , чтобы разрешить внедрение кода. **значение true** используется по умолчанию.

## <a name="remarks"></a>Remarks

Наиболее распространенным применением атрибута **no_injected_text** C++ является параметр компилятора [/FX](../../build/reference/fx-merge-injected-code.md) , который вставляет атрибут **no_injected_text** в MRG-файл.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)
