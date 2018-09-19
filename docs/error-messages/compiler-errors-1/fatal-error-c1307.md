---
title: Неустранимая ошибка C1307 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65f398dd9885c571ea0d66171889f20d3321a3b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085866"
---
# <a name="fatal-error-c1307"></a>Неустранимая ошибка C1307

программа была изменена после сбора данных о профилях

При использовании [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), Компоновщик обнаружил модуль ввода, который был перекомпилирован после/LTCG: PGINSTRUMENT и что модуля был изменен в точку, где данные профиля больше не нужны. Например если в модуле перекомпилированной изменен графа вызовов, компилятор выдаст C1307.

Чтобы устранить эту ошибку, запустите/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и выполните/LTCG: PGOPTIMIZE. Если вам не удается запустить/LTCG: PGINSTRUMENT и вернуть все тестовые запуски, используйте/LTCG: PGUPDATE вместо/LTCG: PGOPTIMIZE для создания оптимизированного образа.