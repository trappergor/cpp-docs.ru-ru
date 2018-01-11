---
title: "4. Переменные среды | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cef1bac78afbcc8b852c3bd42e0904e1963137c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="4-environment-variables"></a>4. Переменные среды
В этой главе описываются переменные среды OpenMP C и C++ API (или эквивалентный механизмы специфический для платформы), контролировать выполнение параллельного кода.  Имена переменных среды должно быть в верхнем регистре. Присвоенные им значения не зависят от регистра и могут иметь начальные и конечные пробелы.  Изменений значений после запуска программы, игнорируются.  
  
 Существуют следующие переменные среды.  
  
-   **OMP_SCHEDULE** задает размер типа и блоков выполнения расписания.  
  
-   **OMP_NUM_THREADS** задает число потоков, используемых во время выполнения.  
  
-   **OMP_DYNAMIC** включает или отключает динамическую настройку потоков.  
  
-   **OMP_NESTED** включает или отключает вложенный параллелизм.  
  
 Примеры в этой главе только демонстрируют, как эти переменные может быть настроена в средах Unix C оболочки (csh). В Korn оболочки и сред DOS действия похожи, следующим образом:  
  
 csh:  
 SetEnv OMP_SCHEDULE «динамический»  
  
 ksh:  
 Экспорт OMP_SCHEDULE = «динамических»  
  
 DOS:  
 задать OMP_SCHEDULE = «динамических»