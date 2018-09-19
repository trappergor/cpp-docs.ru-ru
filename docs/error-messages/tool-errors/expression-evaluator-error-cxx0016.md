---
title: Ошибка вычислителя выражений CXX0016 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0016
dev_langs:
- C++
helpviewer_keywords:
- CAN0016
- CXX0016
ms.assetid: af94a2ae-e835-4da6-8d2f-5c879f72eda2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e03b0567b77b1ef3f64e5cf98cbe11dab502e1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075429"
---
# <a name="expression-evaluator-error-cxx0016"></a>Ошибка вычислителя выражений CXX0016

слишком большая константа

Вычислитель выражений C не может принимать константу целое число без знака, размер которых превышает 4 294 967 295 (0FFFFFFFF в шестнадцатеричной записи), или константы с плавающей запятой, величина которого больше, чем 1.8E + 308.

Эта ошибка идентична ошибке CAN0016.