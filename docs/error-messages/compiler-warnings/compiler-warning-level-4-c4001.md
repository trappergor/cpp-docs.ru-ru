---
title: Предупреждение (уровень 4) C4001 компилятора
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: dd18dc27ee13eab05ea0253c8ebcc990105c15c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401492"
---
# <a name="compiler-warning-level-4-c4001"></a>Предупреждение (уровень 4) C4001 компилятора

было использовано нестандартное расширение «однострочного комментария»

> [!NOTE]
> Это предупреждение удаляется в Visual Studio 2017 версии 15.5, так как однострочные комментарии являются стандартными в C99.

Однострочные комментарии являются стандартными в C++ и стандартная в C, начиная с C99.
В строгом режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), файлы C, содержащие однострочные комментарии, создают ошибку C4001 из-за использования нестандартного расширения. Так как однострочные комментарии являются стандартными в C++, C-файлы, содержащие однострочные комментарии не создают C4001 при компиляции с расширениями Майкрософт (/Ze).

## <a name="example"></a>Пример

Чтобы отключить предупреждение, раскомментируйте [#pragma warning(disable:4001)](../../preprocessor/warning.md).

```
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```