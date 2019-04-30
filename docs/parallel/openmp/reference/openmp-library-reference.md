---
title: Справочные материалы по библиотеке OpenMP
ms.date: 03/20/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: 6f4bbeca54bff1fc44a3576362edca9c30926d5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362521"
---
# <a name="openmp-library-reference"></a>Справочные материалы по библиотеке OpenMP

Ссылки на конструкции, используемые в OpenMP API.

Реализация Visual C++ стандарта OpenMP включает в себя следующие конструкции.

|Конструкция|Описание|
|---------------|-----------------|
|[Директивы](openmp-directives.md)|Ссылки на директивы, используемые в OpenMP API.|
|[Предложения](openmp-directives.md)|Ссылки на предложения, используемые в OpenMP API.|
|[Функции](openmp-functions.md)|Ссылки на функции, используемые в OpenMP API.|
|[Переменные среды](openmp-environment-variables.md)|Ссылки на переменные среды, используемые в OpenMP API.|

Визуальный элемент C++ функции библиотеки времени выполнения OpenMP содержатся в следующих библиотеках.

|Библиотеки времени выполнения OpenMP|Характеристики|
|------------------------------|---------------------|
|VCOMP. LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMP. LIB).|
|VCOMPD.LIB|Многопоточная, динамическая компоновка (библиотека импорта для VCOMPD. КРЫШКИ) (Отладка)|

Если _DEBUG определяется при компиляции и `#include omp.h` в исходном коде, VCOMPD. LIB будет lib по умолчанию, в противном случае VCOMP. LIB будет использоваться.

Можно использовать [/NODEFAULTLIB (пропуск библиотек)](../../../build/reference/nodefaultlib-ignore-libraries.md) для удаления по умолчанию lib и явно выполнять компоновку с lib по своему усмотрению.

Библиотеки OpenMP находятся в каталоге распространяемый компонент Visual C++ и необходимо распространить с приложениями, использующими OpenMP.

## <a name="see-also"></a>См. также

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)