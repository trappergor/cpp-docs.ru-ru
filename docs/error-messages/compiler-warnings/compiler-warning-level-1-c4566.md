---
title: Предупреждение компилятора (уровень 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: c864feb2478e9f99ad6e4c0087dcef72b55de601
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397268"
---
# <a name="compiler-warning-level-1-c4566"></a>Предупреждение компилятора (уровень 1) C4566

символ, представленный универсальное символ имя «char» невозможно представить в текущей кодовой странице (страница)

Не каждый символ Юникода могут быть представлены в текущей кодовой страницы ANSI.

Строку обычных символов (однобайтовых символов) преобразуются в многобайтовых символов, тогда как строки расширенных (двухбайтовых знаков).

Следующий пример приводит к возникновению ошибки C4566:

```
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```