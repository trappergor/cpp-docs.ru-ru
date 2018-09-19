---
title: Предупреждение (уровень 1) C4090 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4090
dev_langs:
- C++
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ae34eeb6c87fdb12b07d25c6b6bbcfdd6b5ee21
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024818"
---
# <a name="compiler-warning-level-1-c4090"></a>Предупреждение (уровень 1) C4090 компилятора

«Операция»: квалификаторы различных «модификатор»

Переменная, которая используется в операции, определяется с помощью указанного модификатора, предотвращает его изменение без обнаружения компилятором. Выражение компилируется без изменений.

Это предупреждение может возникать при создании указателя на **const** или `volatile` не объявлен как указатель на указатель назначен элемент **const** или `volatile`.

Это предупреждение выдается для программ C. В программе на C++ компилятор выдает ошибку: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

Следующий пример приводит к возникновению ошибки C4090:

```
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```