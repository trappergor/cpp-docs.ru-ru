---
title: cpp_quote (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 5a281f9f88412df4d3ee18bff1302b19433e07f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466954"
---
# <a name="cppquote"></a>cpp_quote

Выдает заданную строку, без знаков кавычек в созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Параметры

*statement*<br/>
Инструкцию "C".

## <a name="remarks"></a>Примечания

**Cpp_quote** C++ атрибут полезен, если вы хотите поместить директиву препроцессора в IDL-файле.

Можно также использовать **cpp_quote** и формирования h-файле в процессе компиляции MIDL. Например если файл заголовка C++, который использует атрибуты C++ IDL, но не может использовать этот файл для некоторых задач, после этого можно скомпилировать его, чтобы создать файл созданные MIDL .h, который можно использовать.

**Cpp_quote** атрибут имеет ту же функциональность, что [cpp_quote](/windows/desktop/Midl/cpp-quote) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [двойного](dual.md) пример использования способы использования **cpp_quote**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)