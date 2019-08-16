---
title: cpp_quote (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 905c9fc41b1b42dffe9c7b39fae0b096cdc24950
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501766"
---
# <a name="cpp_quote"></a>cpp_quote

Порождает указанную строку без кавычек в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Параметры

*statement*<br/>
Инструкция C.

## <a name="remarks"></a>Примечания

Атрибут **cpp_quote** C++ полезен, если необходимо поместить директиву препроцессора в IDL-файл.

Можно также использовать **cpp_quote** и создать h файл в составе компиляции MIDL. Например, если имеется файл C++ заголовка, который использует C++ атрибуты IDL, но не может использовать этот файл для некоторой задачи, его можно скомпилировать, чтобы создать h-файл, созданный с помощью MIDL, который вы должны иметь возможность использовать.

Атрибут **cpp_quote** имеет те же функциональные возможности, что и атрибут [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL.

## <a name="example"></a>Пример

См. пример для [Dual](dual.md) в примере использование **cpp_quote**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)