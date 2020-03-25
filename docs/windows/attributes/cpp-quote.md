---
title: cpp_quote (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 451313b5bd1eb5011f1175de5c3bcfe6fb054299
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214920"
---
# <a name="cpp_quote"></a>cpp_quote

Порождает указанную строку без кавычек в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Параметры

*инструкция*<br/>
Инструкция C.

## <a name="remarks"></a>Remarks

Атрибут **cpp_quote** C++ полезен, если необходимо поместить директиву препроцессора в IDL-файл.

Можно также использовать **cpp_quote** и создать h файл в составе компиляции MIDL. Например, если имеется файл C++ заголовка, который использует C++ атрибуты IDL, но не может использовать этот файл для некоторой задачи, его можно скомпилировать, чтобы создать h-файл, созданный с помощью MIDL, который вы должны иметь возможность использовать.

Атрибут **cpp_quote** имеет те же функциональные возможности, что и атрибут [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL.

## <a name="example"></a>Пример

См. пример для [Dual](dual.md) в качестве примера использования **cpp_quote**.

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

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)
