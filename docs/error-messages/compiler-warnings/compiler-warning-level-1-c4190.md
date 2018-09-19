---
title: Предупреждение (уровень 1) C4190 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d398331c159c6fc639160dbe54d6ab5f969d3dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063740"
---
# <a name="compiler-warning-level-1-c4190"></a>Компилятор предупреждение (уровень 1) C4190

«идентификатор1» имеет С-компоновка, но возвращаемый тип UDT «идентификатор2», которая несовместима с C

Функции или указатель на функцию имеет тип возвращаемого значения UDT (определяемый пользователем тип, который является класса, структуры, перечисления или объединения) и `extern` компоновка «C». Это допускается если:

- Все вызовы этой функции происходят из C++.

- Определение функции находится в C++.

## <a name="example"></a>Пример

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```