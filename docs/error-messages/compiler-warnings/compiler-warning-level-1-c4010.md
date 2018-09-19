---
title: Предупреждение (уровень 1) C4010 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52449689d329cee45cc69b63c315ce9335befbe0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073107"
---
# <a name="compiler-warning-level-1-c4010"></a>Компилятор предупреждение (уровень 1) C4010

однострочный комментарий содержит знак продолжения строки

Однострочный комментарий, введенный с / /, содержит обратную косую черту (\\), служит символ продолжения строки. Компилятор считает, что следующая строка продолжением и обрабатывает его как комментарий.

Некоторые синтаксис directed редакторы не указывают строку, следующую символ продолжения как комментарий. Игнорируйте раскраску синтаксических конструкций во всех строках, вызывающих предупреждения.

Следующий пример приводит к возникновению ошибки C4010:

```
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```