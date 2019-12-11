---
title: Предупреждение компилятора (уровень 4) C4001
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: ceb7e65a292e5b9e9ef960ca9553183b703c93f0
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991695"
---
# <a name="compiler-warning-level-4-c4001"></a>Предупреждение компилятора (уровень 4) C4001

использовано нестандартное расширение "однострочный комментарий"

> [!NOTE]
> Это предупреждение удаляется в Visual Studio 2017 версии 15,5, так как однострочные комментарии являются стандартными в C99.

Однострочные комментарии являются стандартными C++ в и в языке C, начиная с C99.
В режиме ограниченной совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) файлы C, содержащие однострочные комментарии, создают C4001 из-за использования нестандартного расширения. Поскольку однострочные комментарии являются стандартными C++в, файлы C, содержащие однострочные комментарии, не создают C4001 при компиляции с расширениями Майкрософт (/Ze).

## <a name="example"></a>Пример

Чтобы отключить предупреждение, раскомментируйте [#pragma warning (Disable: 4001)](../../preprocessor/warning.md).

```cpp
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```
