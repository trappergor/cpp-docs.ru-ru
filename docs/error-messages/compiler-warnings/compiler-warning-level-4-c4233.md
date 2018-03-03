---
title: "Предупреждение (уровень 4) C4233 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad27d2ec3d59df147d8bfc26372a2d25397e651f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4233"></a>Предупреждение компилятора (уровень 4) C4233

> использовано нестандартное расширение: "*ключевое слово*" поддерживается только в C++, C не ключевое слово

Исходный код компилируется как C, а не в C++ и использовать ключевое слово, которое является допустимым только в C++. Компилятор компилирует файла исходного кода как C, если имеет расширение исходного файла c или использовании [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4233 в предупреждение уровня 4, добавьте эту строку в файле исходного кода:

```cpp
#pragma warning(4:4233)
```
