---
title: cpp_quote (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 378435ced5a541785b7b32bc9d2f408034d5a2d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148241"
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