---
title: Ошибка компилятора C2482 | Документы Microsoft
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2c4725dd357854db504272e5b8b9d88641b143d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2482"></a>Ошибка компилятора C2482

>"*идентификатор*": динамическая инициализация данных «thread» не допускается

Это сообщение об ошибке не используется в Visual Studio 2015 и более поздних версиях. В предыдущих версиях, переменные, объявленные с помощью `thread` атрибут нельзя инициализировать с помощью выражения, которое необходимо оценить во время выполнения. Статическое выражение, необходимые для инициализации `thread` данных.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2482 в Visual Studio 2013 и более ранних версий:

```cpp
// C2482.cpp
// compile with: /c
#define Thread __declspec( thread )
Thread int tls_i = tls_i;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
```
