---
title: Предупреждение компилятора (уровень 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: e8765f206d099f808ab261fbbde19273e46b5c90
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051243"
---
# <a name="compiler-warning-level-1-c4829"></a>Предупреждение компилятора (уровень 1) C4829

Возможно, неверные параметры для функции main. Рассмотрим "интмаин (платформа:: массив\<платформа:: строка ^ > ^ argv)"

Некоторые функции, например main, не могут принимать параметры ссылочного типа. Хотя компиляция будет успешной, полученный в результате образ, возможно, не будет выполняться.

Следующий пример приводит к возникновению ошибки C4829.

```cpp
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829
```