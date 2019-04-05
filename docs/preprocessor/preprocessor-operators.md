---
title: Операторы препроцессора
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 0b105cc2039e2aa50c11b796e5474a97d8c5c702
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035693"
---
# <a name="preprocessor-operators"></a>Операторы препроцессора
В контексте директивы `#define` используются четыре оператора, относящихся к препроцессору (краткую информацию о них см. в приведенной ниже таблице). В следующих трех разделах рассматриваются преобразования в строку, преобразования в символы и вставки токенов. Сведения о `defined` оператора, см. в разделе [#if, #elif, #else и #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

|Оператор|Действие|
|--------------|------------|
|[Оператор преобразования в строку (#)](../preprocessor/stringizing-operator-hash.md)|В результате его выполнения соответствующий аргумент заключается в двойные кавычки|
|[Оператор преобразования в символы (#@)](../preprocessor/charizing-operator-hash-at.md)|В результате его выполнения соответствующий аргумент заключается в одиночные кавычки и рассматривается как символ (относится только к системам Microsoft)|
|[Оператор вставки токенов (##)](../preprocessor/token-pasting-operator-hash-hash.md)|Выполняет конкатенацию токенов, используемых в качестве фактических аргументов, для создания других токенов|
|[оператор defined](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Упрощает написание составных выражений в некоторых директивах макросов|

## <a name="see-also"></a>См. также

[Директивы препроцессора](../preprocessor/preprocessor-directives.md)<br/>
[Предустановленный макрос](../preprocessor/predefined-macros.md)<br/>
[Cправочник препроцессора /C++](../preprocessor/c-cpp-preprocessor-reference.md)