---
title: Ошибка компилятора C2026
description: Описывает ошибку компилятора Microsoft C/C++ C2026, ее причины и способы их устранения.
ms.date: 09/25/2020
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: 39195568f964f07c6131fa43ef4a0f06121795da
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414052"
---
# <a name="compiler-error-c2026"></a>Ошибка компилятора C2026

> слишком большая строка, замыкающие символы усечены

Длина строки превышает ограничение в 16380 однобайтовых символов.

## <a name="remarks"></a>Remarks

Перед сцеплением смежных строк длина строки не может превышать 16380 однобайтовых символов.

Строка в Юникоде примерно равна одной половине этой длины также приведет к возникновению этой ошибки.

## <a name="example"></a>Пример

Если имеется строка, определенная следующим образом, создается C2026:

```C
char sz[] =
"\
imagine a really, really \
long string here\
";
```

Его можно разбить следующим образом:

```C
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

Может потребоваться хранить очень большие строковые литералы (32 КБ или более) в настраиваемом ресурсе или внешнем файле. Дополнительные сведения см. [в разделе Создание нового настраиваемого ресурса или ресурсов данных](../../windows/binary-editor.md#to-create-a-new-custom-or-data-resource).
