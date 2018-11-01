---
title: Ошибка вычислителя выражений CXX0039
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 053e57a21f0cb75cbd96732edb6812b3557bcd50
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463275"
---
# <a name="expression-evaluator-error-cxx0039"></a>Ошибка вычислителя выражений CXX0039

символ является неоднозначным

Вычислитель выражений C не может определить, какой экземпляр символа для использования в выражении. Символ возникает несколько раз в дереве наследования.

Необходимо использовать оператор разрешения области (`::`) для явного указания экземпляра для использования в выражении.

Эта ошибка идентична ошибке CAN0039.