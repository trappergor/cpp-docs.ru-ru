---
title: cpp_quote | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00dd1042195bd7593676021cc4f2f1153ec47844
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432858"
---
# <a name="cppquote"></a>cpp_quote

Выдает заданную строку, без знаков кавычек в созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ cpp_quote(
   "statement"
) ];
```

### <a name="parameters"></a>Параметры

*statement*<br/>
Инструкцию "C".

## <a name="remarks"></a>Примечания

**Cpp_quote** C++ атрибут полезен, если вы хотите поместить директиву препроцессора в IDL-файле.

Можно также использовать **cpp_quote** и формирования h-файле в процессе компиляции MIDL. Например если файл заголовка C++, который использует атрибуты C++ IDL, но не может использовать этот файл для некоторых задач, после этого можно скомпилировать его, чтобы создать файл созданные MIDL .h, который можно использовать.

**Cpp_quote** атрибут имеет ту же функциональность, что [cpp_quote](/windows/desktop/Midl/cpp-quote) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [двойного](../windows/dual.md) пример использования способы использования **cpp_quote**.

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

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Изолированные атрибуты](../windows/stand-alone-attributes.md)  