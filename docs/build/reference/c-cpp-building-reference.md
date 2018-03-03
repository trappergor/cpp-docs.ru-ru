---
title: "Ссылка на построение C/C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2269be27dd039357c11d38a2be83b5fc9d6504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cc-building-reference"></a>Ссылка на сборку C/C++
Visual C++ предоставляет два способа построения программ C/C++. Самым простым (и наиболее распространенным) способом является [сборки в среде разработки Visual C++](../../ide/building-cpp-projects-in-visual-studio.md). Другим способом является [построение из командной строки с помощью средства командной строки](../../build/building-on-the-command-line.md). В любом случае можно создать исходные файлы с помощью редактора источника Visual C++ или редактора стороннего по своему усмотрению.  
  
 Если программа использует makefile, а не VCXPROJ-файл, по-прежнему ее сборке можно в среде разработки, как [внешнем проекте](../../ide/building-external-projects.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Компиляция программы на C/C++](../../build/reference/compiling-a-c-cpp-program.md)  
 Описывает компилятор, который создает объектный файл, содержащий машинный код, директивы компоновщика, разделы, внешние ссылки и имена функций и данных.  
  
 [Компоновка](../../build/reference/linking.md)  
 Описывает компоновщик, которое объединяет код из объектные файлы, созданные компилятором, так и статически связанных библиотек, сопоставляет ссылки имен и создает исполняемый файл.  
  
 [Сборки выпуска](../../build/reference/release-builds.md)  
 Представляет сведения о, когда и почему может потребоваться изменить отладочной сборки для сборки выпуска, а также рассматриваются некоторые проблемы, которые могут возникнуть при изменении отладочной сборки выпуска.  
  
 [Оптимизация кода](../../build/reference/optimizing-your-code.md)  
 Содержит ссылки на разделы, посвященные механизмы оптимизации кода:  
  
 [Средства сборки С/C++](../../build/reference/c-cpp-build-tools.md)  
 Предоставляет следующие средства командной строки для просмотра и управления данными выходные данные построения:  
  
 [Ошибки сборки C/C++](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 Представляет раздел ошибок сборки в таблице содержимое.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Справочник по препроцессору в C/C++](../../preprocessor/c-cpp-preprocessor-reference.md)  
 Описывает препроцессор, который подготавливает исходные файлы для компилятора, переведя макросы, операторы и директивы.  
  
 [Сведения об этапах настраиваемой сборки и событиях сборки](../../ide/understanding-custom-build-steps-and-build-events.md)  
 Описывает настройки процесса построения.  
  
 [Построение программы C/C++](../../build/building-c-cpp-programs.md)  
 Содержит ссылки на статьи, в которых описывается процесс сборки программы из командной строки или из интегрированной среды разработки Visual Studio.  
  
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)  
 Описывает настройку параметров компилятора в среде разработки или в командной строке.  
  
 [Параметры компилятора](../../build/reference/compiler-options.md)  
 Ссылки на разделы, в которых обсуждаются параметры компилятора.  
  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)  
 Описывает параметры компоновщика внутри или за пределами интегрированной среды разработки.  
  
 [Параметры компоновщика](../../build/reference/linker-options.md)  
 Ссылки на разделы, в которых обсуждаются параметры компоновщика.  
  
 [Справочник ВSCMAKE](../../build/reference/bscmake-reference.md)  
 Описывает Microsoft утилита просмотра информации (BSCMAKE. (EXE), который создает файл информации (.bsc) из SBR-файлы, созданные во время компиляции.  
  
 [Справочник по LIB](../../build/reference/lib-reference.md)  
 Описывает диспетчер библиотек Microsoft (LIB.exe), который создает и управляет библиотеку общих объектов файла формат COFF объектных файлов.  
  
 [Справочник ЕDITBIN](../../build/reference/editbin-reference.md)  
 Описание редактора файлов Microsoft COFF двоичного файла (программа EDITBIN. (EXE), который изменяет общий объект файла формат COFF двоичных файлов.  
  
 [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md)  
 Описание сборщика данных Microsoft COFF двоичного файла (программа DUMPBIN. (EXE), который содержит сведения о распространенных объекта файла формат COFF двоичных файлов.  
  
 [Справочник по программе NMAKE](../../build/nmake-reference.md)  
 Описание программы обслуживания программы Майкрософт (NMAKE. (EXE), которое представляет собой инструмент, предназначенное для построения проектов на основе команд, содержащихся в файле описания.