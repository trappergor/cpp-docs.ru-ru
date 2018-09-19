---
title: Ошибка компилятора C2085 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d88968e49e38a13782dde2d905a614ad4d177e81
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082382"
---
# <a name="compiler-error-c2085"></a>Ошибка компилятора C2085

«Идентификатор»: не в списке формальных параметров

Идентификатор был объявлен в определении функции, но не в списке формальных параметров. (Только в ANSI C)

Следующий пример приводит к возникновению ошибки C2085:

```
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Возможное решение

```
// C2085b.c
void func1( void );
int main( void ) {}
```

С помощью отсутствует точка с запятой, `func1()` выглядит как определение функции, а не как прототип, поэтому `main` определяется внутри `func1()`, ошибки C2085 для идентификатора `main`.