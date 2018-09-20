---
title: Библиотеки OpenMP | Документация Майкрософт
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
ms.openlocfilehash: c9a4ccfefeaeb9446731027db44b849233bfefd6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391219"
---
# <a name="openmp-libraries"></a>Библиотеки OpenMP

Описывает LIB-файлы, входящие в состав библиотеки среды выполнения OpenMP в Visual C++.

Следующие библиотеки содержат функции библиотеки времени выполнения Visual C++ OpenMP.

|Библиотеки времени выполнения OpenMP|Характеристики|
|------------------------------|---------------------|
|VCOMP. LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMP. LIB).|
|VCOMPD.LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMPD. КРЫШКИ) (Отладка)|

Если _DEBUG определяется при компиляции и `#include omp.h` в исходном коде, VCOMPD. LIB будет по умолчанию lib. В противном случае VCOMP. LIB будет использоваться.

Можно использовать [/NODEFAULTLIB (Ignore Libraries)](../../../build/reference/nodefaultlib-ignore-libraries.md) для удаления по умолчанию lib и явно выполнять компоновку с lib по своему усмотрению.

Библиотеки OpenMP находятся в каталоге распространяемый компонент Visual C++ и необходимо распространить с приложениями, использующими OpenMP.

## <a name="see-also"></a>См. также

[Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)