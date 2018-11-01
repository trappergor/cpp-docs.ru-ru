---
title: Ошибка вычислителя выражений CXX0016
ms.date: 11/04/2016
f1_keywords:
- CXX0016
helpviewer_keywords:
- CAN0016
- CXX0016
ms.assetid: af94a2ae-e835-4da6-8d2f-5c879f72eda2
ms.openlocfilehash: 8e8e8ed3e8b374786414a59bb65e22701b816f65
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493773"
---
# <a name="expression-evaluator-error-cxx0016"></a>Ошибка вычислителя выражений CXX0016

слишком большая константа

Вычислитель выражений C не может принимать константу целое число без знака, размер которых превышает 4 294 967 295 (0FFFFFFFF в шестнадцатеричной записи), или константы с плавающей запятой, величина которого больше, чем 1.8E + 308.

Эта ошибка идентична ошибке CAN0016.