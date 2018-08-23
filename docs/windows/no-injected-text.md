---
title: no_injected_text | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e63b0b47dcc3f53ecd5af2d51505df844f66437a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599390"
---
# <a name="noinjectedtext"></a>no_injected_text

Запрещает компилятору вставку кода в результате использования атрибута.

## <a name="syntax"></a>Синтаксис

```cpp
[ no_injected_text(
   boolean
) ];
```

### <a name="parameters"></a>Параметры

*логическое* (необязательно)  
**значение true,** Если нет кода, подставленного, **false** чтобы кода, которые следует вставить. **значение true,** используется по умолчанию.

## <a name="remarks"></a>Примечания

Наиболее распространенное использование **no_injected_text** C++ атрибут должен быть, [/Fx](../build/reference/fx-merge-injected-code.md) параметр компилятора, который вставляет **no_injected_text** атрибут в MRG-файла.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](../windows/compiler-attributes.md)  