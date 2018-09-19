---
title: Предупреждение (уровень 1) C4020 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4020
dev_langs:
- C++
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef0303c1a811304cd2edaa8622208dc4bada86ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046736"
---
# <a name="compiler-warning-level-1-c4020"></a>Компилятор предупреждение (уровень 1) C4020

«функция»: слишком много фактических параметров

Число фактических параметров в вызове функции превышает количество формальных параметров в прототипе или определении функции. Компилятор передает избыточные фактические параметры в соответствии с соглашение о вызове функции.

Следующий пример приводит к возникновению ошибки C4020:

```
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

Возможное решение

```
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```