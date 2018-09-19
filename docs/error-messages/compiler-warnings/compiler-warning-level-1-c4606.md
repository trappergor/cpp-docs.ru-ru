---
title: Предупреждение компилятора (уровень 1) C4606 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4606
dev_langs:
- C++
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcdaba046f495dc3a29a7c9228edc561674f568f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035998"
---
# <a name="compiler-warning-level-1-c4606"></a>Предупреждение компилятора (уровень 1) C4606

\#в директиве pragma warning: «warning_number» игнорируется; Предупреждения анализа кода не связаны с уровнями предупреждений

Для предупреждения модуля анализа кода, только `error`, `once`, и `default` поддерживаются с [предупреждение](../../preprocessor/warning.md) директивы pragma.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4606.

```
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```