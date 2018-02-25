---
title: "Библиотеки OpenMP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 760e7d138ab71244419ff71960948d4d10f125eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-libraries"></a>Библиотеки OpenMP
Описывает LIB-файлы, входящие в состав библиотеки времени выполнения OpenMP в Visual C++.  
  
 Следующие библиотеки содержат функции библиотеки времени выполнения Visual C++ OpenMP.  
  
|Библиотеки времени выполнения OpenMP|Характеристики|  
|------------------------------|---------------------|  
|VCOMP.LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMP. LIB).|  
|VCOMPD.LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMPD. КРЫШКИ) (Отладка)|  
  
 Если при компиляции определен _DEBUG и `#include omp.h` в исходном коде, VCOMPD. LIB будет по умолчанию lib. В противном случае VCOMP. LIB будет использоваться.  
  
 Можно использовать [/NODEFAULTLIB (пропуск библиотек)](../../../build/reference/nodefaultlib-ignore-libraries.md) для удаления lib по умолчанию и явное связывание с библиотекой по своему усмотрению.  
  
 DLL-библиотеки OpenMP находятся в каталоге распространяемый пакет Visual C++ и необходимо распространить с приложениями, использующими OpenMP.  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)