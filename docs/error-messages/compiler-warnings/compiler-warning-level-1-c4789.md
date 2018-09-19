---
title: Предупреждение компилятора (уровень 1) C4789 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4789
dev_langs:
- C++
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 167bca2a4596a738813309eceb7e22751b5584b8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087335"
---
# <a name="compiler-warning-level-1-c4789"></a>Предупреждение компилятора (уровень 1) C4789

> буфер "*идентификатор*" размера *N* байт будет переполнен; *M* байт будет записано начиная с позиции *L*

## <a name="remarks"></a>Примечания

Предупреждает о переполнения буфера при использовании определенных функций среды CRT, передаче параметров и назначений таким образом, что размеры данных известны во время компиляции. Это предупреждение предназначено для ситуаций, в которых типичные несоответствия размеров данных могут остаться незамеченными.

Предупреждение появляется, если данные, длина которых известна во время компиляции, копируются и помещаются в блок данных, размер которого, известный во время компиляции, слишком мал для этих данных. Копирование необходимо произвести с помощью встроенной формы одной из следующих функций CRT:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Предупреждение также появляется, если тип данных параметра не соответствует при использовании приведения к типу, а затем выполняется попытка присвоения копии из ссылки lvalue.

Visual C++ может показывать данное предупреждение для ветви кода, которое никогда не выполняется. Предупреждение можно временно отключить с помощью `#pragma`, как показано в следующем примере:

```cpp
#pragma(push)
#pragma warning ( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma(pop)
```

Это предотвращает формирование предупреждений для определенного блока кода в Visual C++. `#pragma(push)` сохраняет существующее состояние перед тем, как `#pragma warning(disable: 4789)` изменяет его. `#pragma(pop)` восстанавливает отмененное состояние и устраняет последствия `#pragma warning(disable:4789)`. Дополнительные сведения о директиве препроцессора C++ `#pragma`, см. в разделе [предупреждение](../../preprocessor/warning.md) и [директивы Pragma и ключевое слово __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4789.

```cpp
// C4789.cpp
// compile with: /Oi /W1 /c
#include <string.h>
#include <stdio.h>

int main()
{
    char a[20];
    strcpy(a, "0000000000000000000000000\n");   // C4789

    char buf2[20];
    memset(buf2, 'a', 21);   // C4789

    char c;
    wchar_t w = 0;
    memcpy(&c, &w, sizeof(wchar_t));
}
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4789.

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

void main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```