---
title: Оператор выражений
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
ms.openlocfilehash: 2973c3e0a1cd59edfc7ef1e771454b780da23cf9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562452"
---
# <a name="expression-statement"></a>Оператор выражений

Операторы выражений обеспечивают вычисление выражений. В результате выполнения оператора выражения ни передачи управления, ни итерации не происходит.

Синтаксис оператора выражения простой:

## <a name="syntax"></a>Синтаксис

```
[expression ] ;
```

## <a name="remarks"></a>Примечания

Вычисление всех выражений в операторе выражения и учет всех побочных эффектов осуществляются до выполнения следующего оператора. Самые распространенные операторы выражений — присваивания и вызовы функций.  Поскольку выражение является необязательным, отдельная точка с запятой считается пустым оператором выражения, называются [null](../cpp/null-statement.md) инструкции.

## <a name="see-also"></a>См. также

[Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)