---
title: Неустранимая ошибка C1509 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 837ab5b7cf76b724726c6c52fbfe974d4da6ca85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033138"
---
# <a name="fatal-error-c1509"></a>Неустранимая ошибка C1509

ограничение компилятора: слишком много состояний обработчика исключений в функции «function». Упростите функцию

Код превысил внутреннее ограничение состояний обработчика исключений (32 768 состояний).

Наиболее распространенной причиной является то, что функция содержит сложное выражение определяемого пользователем класса переменные и арифметические операторы.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Упрощение выражений путем назначения общих частей выражения временные переменные.

1. Разбейте функцию на более мелкие функции.