---
title: Предупреждение (уровень 1) C4028 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4028
dev_langs:
- C++
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6c71f04b8f0829bbc321d38a18e4307df51ff0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054744"
---
# <a name="compiler-warning-level-1-c4028"></a>Компилятор предупреждение (уровень 1) C4028

формальный параметр «число» отличается от объявления

Тип формального параметра не совпадает с соответствующим параметром в объявлении. Тип в исходном объявлении используется.

Это предупреждение допустимо только для C исходного кода.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4028.

```
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```