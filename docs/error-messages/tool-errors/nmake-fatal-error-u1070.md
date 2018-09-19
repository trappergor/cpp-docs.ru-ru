---
title: Неустранимая ошибка NMAKE U1070 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6eb462e5c3c7e497cde55151bf92c62ffb2afcd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087023"
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