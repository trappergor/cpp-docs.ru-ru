---
title: Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 09358ee36da7e5a86c214789fa7fd0687e9b8825
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231199"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах

При написании подпрограмм сборки для сопроцессора с плавающей запятой необходимо сохранить управляющее слово с плавающей запятой и очистить стек сопроцессоров, если не возвращать **`float`** **`double`** значение или (которое функция должна возвращать в St (0)).

## <a name="see-also"></a>См. также

[Соглашения о вызовах](../cpp/calling-conventions.md)
