---
title: Операторы препроцессора
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 1c556e4af5913ba8d0dc7efc9648e0d0004d9d7e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222252"
---
# <a name="preprocessor-operators"></a>Операторы препроцессора

В контексте `#define` директивы используются четыре оператора, специфичных для препроцессора. В следующей таблице приведены сводные сведения о каждой из них. В следующих трех разделах рассматриваются преобразования в строку, преобразования в символы и вставки токенов. Дополнительные сведения `defined` об операторе см. [в разделе директивы #if, #elif, #else и #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

|Оператор|Действие|
|--------------|------------|
|[Оператор строковый (#)](../preprocessor/stringizing-operator-hash.md)|В результате его выполнения соответствующий аргумент заключается в двойные кавычки|
|[Оператор преобразования (# @)](../preprocessor/charizing-operator-hash-at.md)|В результате его выполнения соответствующий аргумент заключается в одиночные кавычки и рассматривается как символ (относится только к системам Microsoft)|
|[Оператор для вставления токена (# #)](../preprocessor/token-pasting-operator-hash-hash.md)|Выполняет конкатенацию токенов, используемых в качестве фактических аргументов, для создания других токенов|
|[определенный оператор](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Упрощает написание составных выражений в некоторых директивах макросов|

## <a name="see-also"></a>См. также

[Директивы препроцессора](../preprocessor/preprocessor-directives.md)\
[Предопределенные макросы](../preprocessor/predefined-macros.md)\
[Справочник по препроцессору c/c++](../preprocessor/c-cpp-preprocessor-reference.md)
