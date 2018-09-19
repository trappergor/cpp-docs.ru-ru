---
title: Сборка программ C/C++ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- vcbuilding
- buildingaprogramVC
dev_langs:
- C++
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2792b49d7d3d3f107e39931ff62e6c4137c9c5ca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723272"
---
# <a name="building-cc-programs"></a>Сборка программ C/C++

Вы можете выполнять сборку проектов Visual C++ в Visual Studio или в командной строке. Visual Studio IDE использует [MSBuild](../build/msbuild-visual-cpp.md) для сборки проектов и решений. В командной строке для сборки простых проектов вы можете использовать компилятор C/C++ (cl.exe) и компоновщик (link.exe). Для создания более сложных проектов, в командной строке, можно использовать MSBuild или [NMAKE](../build/nmake-reference.md). Общие сведения о том, как использовать Visual Studio для сборки проектов и решений, см. в разделе [компиляция и сборка](/visualstudio/ide/compiling-and-building-in-visual-studio).

## <a name="in-this-section"></a>В этом разделе

[Построение проектов C++ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md) рассматривается использование Visual Studio IDE для сборки проекта C/C++.

[Построение кода C/C++ в командной строке](../build/building-on-the-command-line.md) описывает, как использовать компилятор командной строки C/C++ и создания средств, включенных в Visual Studio.

[Построение изолированных приложений C/C++ и сборок Side-by-side](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md) описывает модель развертывания для приложения для настольных компьютеров Windows, основанную на идее изолированных приложений и сборок side-by-side.

[Справочник по построения C/C++](../build/reference/c-cpp-building-reference.md) предоставляет ссылки на справочные статьи о сборке программ на C++, параметры компилятора и компоновщика, и различные средства сборки.

[Настройка Visual C++ для 64-разрядная версия, x64 целевых объектов](../build/configuring-programs-for-64-bit-visual-cpp.md) описывает способы настройки Visual Studio и командной строки, чтобы использовать 64-разрядного набора инструментов и как выбрать целевую 64-разрядных архитектур и различные затруднения при перемещении кода на 64-разрядную образцы архитектуры.

[Настройка Visual C++ для процессоров ARM](../build/configuring-programs-for-arm-processors-visual-cpp.md) описываются соглашения, используемые процессорами ARM, а также различные затруднения при перемещении кода в архитектуры ARM.

[Настройка программ для Windows XP](../build/configuring-programs-for-windows-xp.md) описывает способ задания набора инструментов платформы для разработки Windows XP.

## <a name="related-sections"></a>Связанные разделы

[Компиляция и сборка](/visualstudio/ide/compiling-and-building-in-visual-studio) описывает системы и средств сборки Visual Studio.