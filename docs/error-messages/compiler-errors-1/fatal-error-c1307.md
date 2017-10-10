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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1173f538f02e8178d523bb51476b4a10427099ea
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1307"></a>Неустранимая ошибка C1307
программа была изменена после сбора данных о профилях  
  
 При использовании [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), Компоновщик обнаружил модуль ввода, который был перекомпилирован после/LTCG: PGINSTRUMENT и используемого модуля в точке, где данные профиля больше не нужны. Например изменении графа вызовов в модуле перекомпилированной компилятор выдаст C1307.  
  
 Чтобы устранить эту ошибку, запустите/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и запустите/LTCG: PGOPTIMIZE. Если вы не удается запустить/LTCG: PGINSTRUMENT и вернуть все тестовые запуски, используйте/LTCG: PGUPDATE вместо/LTCG: PGOPTIMIZE для создания оптимизированного образа.
