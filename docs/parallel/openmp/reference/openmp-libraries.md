---
title: Библиотеки OpenMP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46bd287ff8a020a4d5d7775afdb12f5571d43294
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694775"
---
# <a name="openmp-libraries"></a>Библиотеки OpenMP
Описывает LIB-файлы, входящие в состав библиотеки времени выполнения OpenMP в Visual C++.  
  
 Следующие библиотеки содержат функции библиотеки времени выполнения Visual C++ OpenMP.  
  
|Библиотеки времени выполнения OpenMP|Характеристики|  
|------------------------------|---------------------|  
|VCOMP. LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMP. LIB).|  
|VCOMPD.LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMPD. КРЫШКИ) (Отладка)|  
  
 Если при компиляции определен _DEBUG и `#include omp.h` в исходном коде, VCOMPD. LIB будет по умолчанию lib. В противном случае VCOMP. LIB будет использоваться.  
  
 Можно использовать [/NODEFAULTLIB (пропуск библиотек)](../../../build/reference/nodefaultlib-ignore-libraries.md) для удаления lib по умолчанию и явное связывание с библиотекой по своему усмотрению.  
  
 DLL-библиотеки OpenMP находятся в каталоге распространяемый пакет Visual C++ и необходимо распространить с приложениями, использующими OpenMP.  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)