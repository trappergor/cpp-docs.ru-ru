---
title: "Преимуществами и недостатками метод, используемый для связи с этой библиотекой CRT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 244415a947918a836e8c4c67dbd18758ec40393c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Преимуществами и недостатками метод, используемый для связи с этой библиотекой CRT
Проект можно связать с CRT статически или динамически. В следующей таблице описаны преимущества и недостатки, по выбору подходящего метода.  
  
|Метод|Преимущество|Компромисс|  
|------------|-------------|--------------|  
|Статическая компоновка с библиотекой CRT<br /><br /> (**Библиотеки времени выполнения** значение **однопоточных**)|CRT DLL в системе, где будет выполняться изображение не требуется.|Около 25 КБ код запуска добавляется в образ, незначительно увеличив его размер.|  
|Динамическая компоновка с библиотекой CRT<br /><br /> (**Библиотеки времени выполнения** значение **многопоточных**)|Образ не требует код запуска CRT, поэтому гораздо меньше.|CRT DLL должна находиться на системы под управлением образа.|  
  
 Раздел [связывание с CRT в ATL проект](../atl/linking-to-the-crt-in-your-atl-project.md) описывается выберите способ для связи с этой библиотекой CRT.  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием ATL и кода среды выполнения C](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Библиотеки DLL и поведение библиотеки времени выполнения Visual C++](../build/run-time-library-behavior.md)   
 [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)

