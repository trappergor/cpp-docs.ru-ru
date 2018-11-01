---
title: Неустранимая ошибка NMAKE U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 35bea47f6626dfe283a537d3d96340921c37f3f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484218"
---
# <a name="nmake-fatal-error-u1070"></a>Неустранимая ошибка NMAKE U1070

Циклическая зависимость в макроопределении «имя макроса»

Указанное Макроопределение содержит макрос, определение которого содержится оно само. Циклическое определение макросов являются недопустимыми.

## <a name="example"></a>Пример

Следующие определения макросов

```
ONE=$(TWO)
TWO=$(ONE)
```

возникает следующая ошибка:

```
cycle in macro definition 'TWO'
```