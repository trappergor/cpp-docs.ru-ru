---
title: Общие сведения об операторах в C
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
ms.openlocfilehash: 1b5863a021fd74bb80162d589af7c2a1a5b36f9b
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147052"
---
# <a name="overview-of-c-statements"></a>Общие сведения об операторах в C

Операторы языка C состоят из токенов, выражений и других операторов. Оператор, который формирует компонент или другой оператор, называется телом внешнего оператора. В этом разделе рассматриваются все типы операторов, которые задаются следующим синтаксисом:

## <a name="syntax"></a>Синтаксис

*statement*: [labeled-statement](../c-language/goto-and-labeled-statements-c.md)

[compound-statement](../c-language/compound-statement-c.md)

[expression-statement](../c-language/expression-statement-c.md)

[selection-statement](../c-language/if-statement-c.md)

[iteration-statement](../c-language/do-while-statement-c.md)

[jump-statement](../c-language/break-statement-c.md)

[try-except-statement](../c-language/try-except-statement-c.md)

/* Относится только к системам Microsoft \*/[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Относится только к системам Microsoft \*/

Тело оператора часто представляет собой составной оператор, то есть состоит из других операторов, которые могут содержать ключевые слова. Составные операторы разграничиваются фигурными скобками (**{ }**). Все остальные операторы C заканчиваются точкой с запятой (**;**). Точка с запятой является признаком конца оператора.

Оператор выражения содержит выражение на языке C, которое может содержать арифметические или логические операторы, представленные в статье [Выражения и присваивания](../c-language/expressions-and-assignments.md). Неопределенный оператор представляет собой пустой оператор.

Любой оператор C может начинаться с метки-идентификатора, которая состоит из имени и двоеточия. Поскольку метки операторов распознает только оператор `goto`, они рассматриваются в разделе, посвященном оператору `goto`. Дополнительные сведения см. в статье [goto и помеченные операторы (C)](../c-language/goto-and-labeled-statements-c.md).

## <a name="see-also"></a>См. также

[Операторы](../c-language/statements-c.md)
