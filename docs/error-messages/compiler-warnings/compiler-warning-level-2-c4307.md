---
title: Предупреждение компилятора (уровень 2) C4307 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4307
dev_langs:
- C++
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed18c213b35e79aaae98efa5932ac404a8d84bff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079197"
---
# <a name="compiler-warning-level-2-c4307"></a>Предупреждение компилятора (уровень 2) C4307

«operator»: переполнение целой константы

Оператор, используемый в выражении, приводит к целочисленной константой переполнение памяти, выделенной для него. Может потребоваться использовать больший тип константы. Объект **целочисленное число со знаком** содержит меньше, чем значение `unsigned int` поскольку **целочисленное число со знаком** один бит используется для представления знака.

Следующий пример приводит к возникновению ошибки C4307:

```
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```