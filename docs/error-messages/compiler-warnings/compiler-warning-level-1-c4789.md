---
title: Предупреждение компилятора (уровень 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: 36a5032098c5caabb1b050833e487fd58679a782
ms.sourcegitcommit: 6e4dd21759caaed262a7255735cf8d6e8fb9f4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476859"
---
# <a name="compiler-warning-level-1-c4789"></a>Предупреждение компилятора (уровень 1) C4789

> буфер "*идентификатор*" размера *N* байт будет переполнен; *M* байт будет записано начиная с позиции *L*

## <a name="remarks"></a>Примечания

**C4789** предупреждает о переполнения буфера, при использовании определенных функций C времени выполнения (CRT). Он может также указывать размер несоответствия, когда параметры передаются или назначений. Предупреждение возможна в том случае, если размеры данных известны во время компиляции. Это предупреждение предназначено для ситуаций, в которых типичные несоответствия размеров данных могут остаться незамеченными.

**C4789** выдает предупреждение, когда данные копируются в блок данных, слишком мал известно во время компиляции.

Это предупреждение возникает, если копия используется встроенной формы одной из этих функций CRT:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Предупреждение появляется также в том случае, если вы привести параметр к большему типу данных, а затем внесите присвоения копии из ссылки lvalue.

Visual C++ может показывать данное предупреждение для ветви кода, который никогда не выполняется. Предупреждение можно временно отключить с помощью `#pragma`, как показано в следующем примере:

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

Эту идиому предотвращает Формирование предупреждений для определенного блока кода Visual C++. `#pragma warning(push)` сохраняет существующее состояние перед тем, как `#pragma warning(disable: 4789)` изменяет его. `#pragma warning(pop)` восстанавливает отмененное состояние и устраняет последствия `#pragma warning(disable:4789)`. Дополнительные сведения о директиве препроцессора C++ `#pragma`, см. в разделе [предупреждение](../../preprocessor/warning.md) и [директивы Pragma и ключевое слово __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

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