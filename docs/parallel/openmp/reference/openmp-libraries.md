---
title: "OpenMP Libraries | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Libraries
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Описывает lib\-файлы, составляющих библиотеки времени выполнения OpenMP in Visual C\+\+.  
  
 Следующие библиотеки содержат функции библиотеки времени выполнения Visual C\+\+ OpenMP.  
  
|Библиотека времени выполнения OpenMP|Характеристики|  
|------------------------------------------|--------------------|  
|VCOMP.LIB|Многопоточные, динамическая ссылка \(библиотека импорта для VCOMP.LIB\).|  
|VCOMPD.LIB|Многопоточные, динамическая ссылка \(библиотека импорта для VCOMPD.LID\) \(отладка\)|  
  
 Если \_DEBUG определен в компиляции и если `#include omp.h` в исходном коде VCOMPD.LIB по умолчанию свободой.  В противном случае \- значение VCOMP.LIB будет использоваться.  
  
 Можно использовать [Параметр \/NODEFAULTLIB \(пропуск библиотек\)](../../../build/reference/nodefaultlib-ignore-libraries.md) удалить по умолчанию lib и явно связать с свободой.  
  
 Библиотека DLL OpenMP в каталоге Visual C\+\+ для распространения и должны быть распределянным с приложениями, которые используют OpenMP.  
  
## См. также  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)