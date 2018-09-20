---
title: Операторы препроцессора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b80c9c8ef371808fc98d0475afc00223b13194ea
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384043"
---
# <a name="preprocessor-operators"></a>Операторы препроцессора
В контексте директивы `#define` используются четыре оператора, относящихся к препроцессору (краткую информацию о них см. в приведенной ниже таблице). В следующих трех разделах рассматриваются преобразования в строку, преобразования в символы и вставки токенов. Сведения о `defined` оператора, см. в разделе [#if, #elif, #else и #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
|Оператор|Действие|  
|--------------|------------|  
|[Строковый оператор (#)](../preprocessor/stringizing-operator-hash.md)|В результате его выполнения соответствующий аргумент заключается в двойные кавычки|  
|[Оператор преобразования в символы (#@)](../preprocessor/charizing-operator-hash-at.md)|В результате его выполнения соответствующий аргумент заключается в одиночные кавычки и рассматривается как символ (относится только к системам Microsoft)|  
|[Оператор вставки токена (##)](../preprocessor/token-pasting-operator-hash-hash.md)|Выполняет конкатенацию токенов, используемых в качестве фактических аргументов, для создания других токенов|  
|[определенный оператор](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Упрощает написание составных выражений в некоторых директивах макросов|  
  
## <a name="see-also"></a>См. также  
 
[Директивы препроцессора](../preprocessor/preprocessor-directives.md)<br/>
[Предопределенные макросы](../preprocessor/predefined-macros.md)<br/>
[Справочник по препроцессору в C/C++](../preprocessor/c-cpp-preprocessor-reference.md)