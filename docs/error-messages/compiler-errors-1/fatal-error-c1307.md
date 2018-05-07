---
title: Неустранимая ошибка C1307 | Документы Microsoft
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
ms.openlocfilehash: 9d06ce51ada7cd9159b8e02ff627bf12ebb7293d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1307"></a>Неустранимая ошибка C1307
программа была изменена после сбора данных о профилях  
  
 При использовании [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), Компоновщик обнаружил модуль ввода, который был перекомпилирован после/LTCG: PGINSTRUMENT и используемого модуля в точке, где данные профиля больше не нужны. Например изменении графа вызовов в модуле перекомпилированной компилятор выдаст C1307.  
  
 Чтобы устранить эту ошибку, запустите/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и запустите/LTCG: PGOPTIMIZE. Если вы не удается запустить/LTCG: PGINSTRUMENT и вернуть все тестовые запуски, используйте/LTCG: PGUPDATE вместо/LTCG: PGOPTIMIZE для создания оптимизированного образа.