---
title: Ошибка компилятора C3452
ms.date: 11/04/2016
f1_keywords:
- C3452
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
ms.openlocfilehash: 165c031f23f3b317300900970b30414da42e7840
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397449"
---
# <a name="compiler-error-c3452"></a>Ошибка компилятора C3452

член аргумента списка не является константой

Аргумент передан в атрибут, ожидающий константу, значение которого можно вычислить во время компиляции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3452:

```
// C3452.cpp
// compile with: /c
int i;
[module( name="mod", type=dll, custom={i} ) ];   // C3452
// try the following line instead
// [module( name="mod", type=dll, custom={"a"} ) ];
```