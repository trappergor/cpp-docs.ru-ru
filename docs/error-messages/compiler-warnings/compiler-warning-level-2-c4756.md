---
title: Предупреждение компилятора (уровень 2) C4756 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4756
dev_langs:
- C++
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b80596ede2cc93e64b79b1d5c08e091a880c7771
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086620"
---
# <a name="compiler-warning-level-2-c4756"></a>Предупреждение компилятора (уровень 2) C4756

Переполнение при расчете констант

Компилятор создает исключение при выполнении расчета константного выражения во время компиляции.

Следующий пример приводит к возникновению ошибки C4756:

```
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```