---
title: "Предупреждение (уровень 4) C4233 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4233
dev_langs: C++
helpviewer_keywords: C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 16e32686451ba7ce0c9a633878f1158a8457163a
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2017
---
# <a name="compiler-warning-level-4-c4233"></a>Предупреждение компилятора (уровень 4) C4233

> использовано нестандартное расширение: "*ключевое слово*" поддерживается только в C++, C не ключевое слово

Исходный код компилируется как C, а не в C++ и использовать ключевое слово, которое является допустимым только в C++. Компилятор компилирует файла исходного кода как C, если имеет расширение исходного файла c или использовании [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4233 в предупреждение уровня 4, добавьте эту строку в файле исходного кода:

```cpp
#pragma warning(4:4233)
```
