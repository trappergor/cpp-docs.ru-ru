---
title: Предупреждение компилятора (уровень 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: 87d610980ffe9d9e5087ddaec0ecb91d813a4d60
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162262"
---
# <a name="compiler-warning-level-1-c4566"></a>Предупреждение компилятора (уровень 1) C4566

символ, представленный универсальным именем символа "char", не может быть представлен в текущей кодовой странице (страница)

Не каждый символ Юникода может быть представлен в текущей кодовой странице ANSI.

Узкие строки (однобайтовые символы) преобразуются в многобайтовые символы, а широкие строки (двухбайтовые символы) — нет.

Следующий пример приводит к возникновению ошибки C4566:

```cpp
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```
