---
title: Предупреждение (уровень 3) C4018 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4018
dev_langs:
- C++
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99ca94a47925a64c91077ad5b363e953def186b1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041328"
---
# <a name="compiler-warning-level-3-c4018"></a>Компилятор предупреждение (уровень 3) C4018

«выражение»: несоответствие со знаком и без

Сравнивает номер со знаком и без знака требуется компилятору преобразовать значение со знаком в числа без знака.

Чтобы устранить это предупреждение, приведен один из двух типов при тестировании типов со знаком и без знака.

Следующий пример приводит к возникновению ошибки C4018:

```
// C4018.cpp
// compile with: /W3
int main() {
   unsigned int uc = 0;
   int c = 0;
   unsigned int c2 = 0;

   if (uc < c) uc = 0;   // C4018

   // OK
   if (uc == c2) uc = 0;
}
```