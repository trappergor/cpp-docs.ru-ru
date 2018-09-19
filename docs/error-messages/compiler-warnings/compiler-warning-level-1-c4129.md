---
title: Предупреждение (уровень 1) C4129 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e02f38044180c45e221099d2874b7f8ff48d62f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098450"
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