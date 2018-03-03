---
title: "Неустранимая ошибка C1307 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe97f1658a74b0db5985ed755bf387811f2c6d1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1307"></a>Неустранимая ошибка C1307
программа была изменена после сбора данных о профилях  
  
 При использовании [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), Компоновщик обнаружил модуль ввода, который был перекомпилирован после/LTCG: PGINSTRUMENT и используемого модуля в точке, где данные профиля больше не нужны. Например изменении графа вызовов в модуле перекомпилированной компилятор выдаст C1307.  
  
 Чтобы устранить эту ошибку, запустите/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и запустите/LTCG: PGOPTIMIZE. Если вы не удается запустить/LTCG: PGINSTRUMENT и вернуть все тестовые запуски, используйте/LTCG: PGUPDATE вместо/LTCG: PGOPTIMIZE для создания оптимизированного образа.