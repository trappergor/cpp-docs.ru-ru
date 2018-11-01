---
title: Компилятор предупреждение (уровень 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: dc4f4c4c1feeba543ce0baa71e1ee5dfd81fdcae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428681"
---
# <a name="compiler-warning-level-1-c4129"></a>Компилятор предупреждение (уровень 1) C4129

«символ»: неизвестная escape-последовательность

`character` После обратной косой черты (\\) в символьной или строковой константы не распознается как допустимое escape-последовательность. Обратная косая черта пропускается и не печатаются. Выводится символ после обратной косой черты.

Для печати одной обратной косой черты, укажите двойная обратная косая черта (\\\\).

Стандарт языка C++, в разделе 2.13.2 рассматриваются escape-последовательности.

Следующий пример приводит к возникновению ошибки C4129:

```
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```