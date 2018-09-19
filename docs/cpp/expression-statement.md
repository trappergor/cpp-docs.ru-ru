---
title: Оператор выражения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f026a91846196e34f97b4d2cbcfa2c9fa749e8b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058611"
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