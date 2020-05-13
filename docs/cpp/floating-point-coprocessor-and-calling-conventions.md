---
title: Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: c70dd3b049ca353acc8a504df52b2c61feaf1974
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188628"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах

При написании подпрограмм сборки для сопроцессора с плавающей точкой необходимо сохранить управляющее слово с плавающей запятой и очистить стек сопроцессоров, если не возвращать значение **типа float** или **Double** (которое функция должна возвращать в St (0)).

## <a name="see-also"></a>См. также раздел

[Соглашения о вызовах](../cpp/calling-conventions.md)
