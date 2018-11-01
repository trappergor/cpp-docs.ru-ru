---
title: Сборка программ C/C++
ms.date: 11/04/2016
f1_keywords:
- vcbuilding
- buildingaprogramVC
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
ms.openlocfilehash: 79f799fc643d931555bc8c2c56fa9ba5f51b63a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558344"
---
# <a name="building-cc-programs"></a>Сборка программ C/C++

Вы можете выполнять сборку проектов Visual C++ в Visual Studio или в командной строке. Visual Studio IDE использует [MSBuild](../build/msbuild-visual-cpp.md) для сборки проектов и решений. В командной строке для сборки простых проектов вы можете использовать компилятор C/C++ (cl.exe) и компоновщик (link.exe). Для создания более сложных проектов, в командной строке, можно использовать MSBuild или [NMAKE](../build/nmake-reference.md). Общие сведения о том, как использовать Visual Studio для сборки проектов и решений, см. в разделе [компиляция и сборка](/visualstudio/ide/compiling-and-building-in-visual-studio).

## <a name="in-this-section"></a>В этом разделе

[Сборка проектов C++ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)<br/>
Описывает использование среды IDE Visual Studio для сборки проекта C/C++.

[Создание кода C/C++ в командной строке](../build/building-on-the-command-line.md)<br/>
Описывает использование средств сборки и компилятора командной строки C/C++, входящих в состав Visual Studio.

[Создание изолированных приложений и параллельных сборок C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)<br/>
Описывает модель развертывания для классических приложений Windows, основанную на концепции изолированных приложений и параллельных сборок.

[Справочные сведения о сборке C/C++](../build/reference/c-cpp-building-reference.md)<br/>
Содержит ссылки на справочные статьи о сборке программ на C++, о параметрах компилятора и компоновщика, а также о различных средствах сборки.

[Настройка Visual C++ для 64-разрядных целевых объектов с архитектурой x64](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
Описывает настройку Visual Studio и командной строки для использования 64-разрядного набора инструментов и создание программ для 64-разрядных архитектур, а также различные затруднения при переносе кода на 64-разрядные архитектуры.

[Настройка Visual C++ для процессоров ARM](../build/configuring-programs-for-arm-processors-visual-cpp.md)<br/>
Описывает соглашения, используемые процессорами ARM, а также содержит обзор распространенных проблем миграции, возникающих при перемещении кода в архитектуры ARM.

[Настройка программ для Windows XP](../build/configuring-programs-for-windows-xp.md)<br/>
Описывает настройку набора инструментов платформы для ориентации на разработку под Windows XP.

## <a name="related-sections"></a>Связанные разделы

[Компилирование и сборка](/visualstudio/ide/compiling-and-building-in-visual-studio)<br/>
Описывает систему сборки и средства Visual Studio.