---
title: Неустранимая ошибка C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: 1acdda77ac9cbf8d99752de3b78ab9c32bbb4cbc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552273"
---
# <a name="fatal-error-c1307"></a>Неустранимая ошибка C1307

программа была изменена после сбора данных о профилях

При использовании [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), Компоновщик обнаружил модуль ввода, который был перекомпилирован после/LTCG: PGINSTRUMENT и что модуля был изменен в точку, где данные профиля больше не нужны. Например если в модуле перекомпилированной изменен графа вызовов, компилятор выдаст C1307.

Чтобы устранить эту ошибку, запустите/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и выполните/LTCG: PGOPTIMIZE. Если вам не удается запустить/LTCG: PGINSTRUMENT и вернуть все тестовые запуски, используйте/LTCG: PGUPDATE вместо/LTCG: PGOPTIMIZE для создания оптимизированного образа.