---
title: Построение программ C/C++ | Документы Microsoft
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
ms.openlocfilehash: 2894c503dde89668bfb90b615c7b0966fe5fe2e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360979"
---
# <a name="building-cc-programs"></a>Сборка программ C/C++

Вы можете выполнять сборку проектов Visual C++ в Visual Studio или в командной строке. Интегрированная среда разработки Visual Studio использует [MSBuild](../build/msbuild-visual-cpp.md) для построения проектов и решений. В командной строке для сборки простых проектов вы можете использовать компилятор C/C++ (cl.exe) и компоновщик (link.exe). Для создания более сложных проектов в командной строке, можно использовать MSBuild или [NMAKE](../build/nmake-reference.md). Общие сведения об использовании [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] для построения проектов и решений, в разделе [компилирование и сборка](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
## <a name="in-this-section"></a>В этом разделе  

[Сборка проектов C++ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)  
Описывает использование среды IDE Visual Studio для сборки проекта C/C++.  
  
[Создание кода C/C++ в командной строке](../build/building-on-the-command-line.md)  
Описывает использование средств сборки и компилятора командной строки C/C++, входящих в состав Visual Studio.  
  
[Создание изолированных приложений и параллельных сборок C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
Описывает модель развертывания для классических приложений Windows, основанную на концепции изолированных приложений и параллельных сборок.  
  
[Справочные сведения о сборке C/C++](../build/reference/c-cpp-building-reference.md)  
Содержит ссылки на справочные статьи о сборке программ на C++, о параметрах компилятора и компоновщика, а также о различных средствах сборки.  
  
[Настройка Visual C++ для 64-разрядных целевых объектов с архитектурой x64](../build/configuring-programs-for-64-bit-visual-cpp.md)  
Описывает настройку Visual Studio и командной строки для использования 64-разрядного набора инструментов и создание программ для 64-разрядных архитектур, а также различные затруднения при переносе кода на 64-разрядные архитектуры.  
  
[Настройка Visual C++ для процессоров ARM](../build/configuring-programs-for-arm-processors-visual-cpp.md)  
Описывает соглашения, используемые процессорами ARM, а также содержит обзор распространенных проблем миграции, возникающих при перемещении кода в архитектуры ARM.  
  
[Настройка программ для Windows XP](../build/configuring-programs-for-windows-xp.md)  
Описывает настройку набора инструментов платформы для ориентации на разработку под Windows XP.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компилирование и сборка](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Описывает систему сборки и средства Visual Studio.