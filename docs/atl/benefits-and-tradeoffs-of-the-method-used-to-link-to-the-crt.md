---
title: Преимуществами и недостатками метод, используемый для связи с этой библиотекой CRT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2835e88da11b8d8332226080eb860afd41c0702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

