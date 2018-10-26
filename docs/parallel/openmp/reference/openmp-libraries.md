---
title: Библиотеки OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 7620b0ea710a5474fbbbf614691ceeb1e5cc945e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062006"
---
# <a name="openmp-libraries"></a>Библиотеки OpenMP

Описывает LIB-файлы, входящие в состав библиотеки среды выполнения OpenMP в Visual C++.

Следующие библиотеки содержат функции библиотеки времени выполнения Visual C++ OpenMP.

|Библиотеки времени выполнения OpenMP|Характеристики|
|------------------------------|---------------------|
|VCOMP. LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMP. LIB).|
|VCOMPD.LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMPD. КРЫШКИ) (Отладка)|

Если _DEBUG определяется при компиляции и `#include omp.h` в исходном коде, VCOMPD. LIB будет по умолчанию lib. В противном случае VCOMP. LIB будет использоваться.

Можно использовать [/NODEFAULTLIB (пропуск библиотек)](../../../build/reference/nodefaultlib-ignore-libraries.md) для удаления по умолчанию lib и явно выполнять компоновку с lib по своему усмотрению.

Библиотеки OpenMP находятся в каталоге распространяемый компонент Visual C++ и необходимо распространить с приложениями, использующими OpenMP.

## <a name="see-also"></a>См. также

[Справочник по библиотеке](openmp-library-reference.md)
