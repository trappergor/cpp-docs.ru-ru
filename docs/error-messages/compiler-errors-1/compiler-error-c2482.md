---
title: "Ошибка компилятора C2482 | Документы Microsoft"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2482
dev_langs: C++
helpviewer_keywords: C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c4a5d081e7a19f09f10e40e3799f724f44b295fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
