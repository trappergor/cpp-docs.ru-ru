---
title: "3. Функции библиотеки времени выполнения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1cbedf8782c9c5ccb25bda3f8b43df8a526f268
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="3-run-time-library-functions"></a>3. Функции библиотеки времени выполнения
В этом разделе описываются функции библиотеки CRT, OpenMP C и C++. Заголовок  **\<omp.h >** объявляются два типа, несколько функций, которые можно использовать для управления и запросить среду параллельного выполнения и заблокировать функций, которые можно использовать для синхронизации доступа к данным.  
  
 Тип **omp_lock_t** не является типом объекта, способный представлять, что блокировка доступен или поток владеет блокировкой. Эти блокировки, называются *простые блокировки*.  
  
 Тип **omp_nest_lock_t** тип объекта, способный представлять, доступно блокировки или идентификатора потока, который владеет блокировкой и *вложенности счетчик* (как описано ниже). Эти блокировки, называются *блокировки, которая*.  
  
 Функции библиотеки являются внешние функции с компоновкой «C».  
  
 Описания в этой главе делятся на следующие разделы:  
  
-   Функции среды выполнения (в разделе [разделе 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) на странице 35).  
  
-   Заблокировать функции (см. [разделе 3.2](../../parallel/openmp/3-2-lock-functions.md) на странице 41).