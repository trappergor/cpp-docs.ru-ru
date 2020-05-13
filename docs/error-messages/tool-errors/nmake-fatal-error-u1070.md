---
title: Неустранимая ошибка NMAKE U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 008d49df3460cb7cf760e4b278db20da444555fe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182777"
---
# <a name="nmake-fatal-error-u1070"></a>Неустранимая ошибка NMAKE U1070

цикл в определении макроса "имямакроса"

Заданное определение макроса содержит макрос, определение которого содержало данный макрос. Недопустимые циклические определения макросов.

## <a name="example"></a>Пример

Следующие определения макросов

```
ONE=$(TWO)
TWO=$(ONE)
```

приводит к следующей ошибке:

```
cycle in macro definition 'TWO'
```
