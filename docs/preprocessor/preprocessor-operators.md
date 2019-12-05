---
title: Операторы препроцессора
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 5dd252fb495a05efe6eef45674f9ecd601a298a7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857948"
---
# <a name="preprocessor-operators"></a>Операторы препроцессора

В контексте директивы `#define` используются четыре оператора, специфичных для препроцессора. В следующей таблице приведены сводные сведения о каждой из них. В следующих трех разделах рассматриваются преобразования в строку, преобразования в символы и вставки токенов. Дополнительные сведения об операторе `defined` см. [в разделе #if, #elif, #else и директивы #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

|оператора|Действие|
|--------------|------------|
|[Оператор строковый (#)](../preprocessor/stringizing-operator-hash.md)|В результате его выполнения соответствующий аргумент заключается в двойные кавычки|
|[Оператор преобразования (# @)](../preprocessor/charizing-operator-hash-at.md)|Заставляет соответствующий аргумент заключаться в одинарные кавычки и обрабатываться как символ (для конкретного приложения).|
|[Оператор для вставления токена (# #)](../preprocessor/token-pasting-operator-hash-hash.md)|Выполняет конкатенацию токенов, используемых в качестве фактических аргументов, для создания других токенов|
|[определенный оператор](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Упрощает написание составных выражений в некоторых директивах макросов|

## <a name="see-also"></a>См. также:

[Директивы препроцессора](../preprocessor/preprocessor-directives.md)\
[Предопределенные макросы](../preprocessor/predefined-macros.md)\
[Справочник по препроцессору c/c++](../preprocessor/c-cpp-preprocessor-reference.md)
