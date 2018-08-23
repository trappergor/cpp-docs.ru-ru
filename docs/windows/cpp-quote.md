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
ms.openlocfilehash: 8a1b9ba00c8728c86935b7c64105d03bb4f19b10
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610604"
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

*statement*  
Инструкцию "C".

## <a name="remarks"></a>Примечания

**Cpp_quote** C++ атрибут полезен, если вы хотите поместить директиву препроцессора в IDL-файле.

Можно также использовать **cpp_quote** и формирования h-файле в процессе компиляции MIDL. Например если файл заголовка C++, который использует атрибуты C++ IDL, но не может использовать этот файл для некоторых задач, после этого можно скомпилировать его, чтобы создать файл созданные MIDL .h, который можно использовать.

**Cpp_quote** атрибут имеет ту же функциональность, что [cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) описании атрибута MIDL.

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

[Атрибуты IDL](../windows/idl-attributes.md)  
[Изолированные атрибуты](../windows/stand-alone-attributes.md)  