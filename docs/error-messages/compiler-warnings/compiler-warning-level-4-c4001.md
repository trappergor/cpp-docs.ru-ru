---
title: Предупреждение (уровень 4) C4001 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c325656b9e61ee324a3b9f171413f1020440f9ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025416"
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