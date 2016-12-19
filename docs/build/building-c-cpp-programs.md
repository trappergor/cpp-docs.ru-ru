---
title: "Сборка программ C/C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vcbuilding"
  - "buildingaprogramVC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "построения [C++]"
  - "построения [C++], параметры"
  - "проекты [C++], построение"
  - "проекты Visual C++, построение"
  - "Visual C++, параметры построения"
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Сборка программ C/C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вы можете выполнять сборку проектов Visual C\+\+ в Visual Studio или в командной строке.  Среда IDE Visual Studio использует систему [MSBuild](../Topic/MSBuild%20\(Visual%20C++\).md) для сборки проектов и решений.  В командной строке для сборки простых проектов вы можете использовать компилятор C\/C\+\+ \(cl.exe\) и компоновщик \(link.exe\).  Для сборки более сложных проектов в командной строке можно использовать MSBuild или [NMAKE](../build/nmake-reference.md).  Сведения об использовании [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] для сборки проектов и решений см. в разделе [Построение приложений в Visual Studio](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md).  
  
## В этом подразделе  
 [Построение проектов C\+\+ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)  
 Описывает использование среды IDE Visual Studio для сборки проекта C\/C\+\+.  
  
 [Построение из командной строки](../Topic/Building%20on%20the%20Command%20Line.md)  
 Описывает использование средств сборки и компилятора командной строки C\/C\+\+, входящих в состав Visual Studio.  
  
 [Построение изолированных приложений и параллельных сборок C\/C\+\+](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
 Описывает модель развертывания для классических приложений Windows, основанную на концепции изолированных приложений и параллельных сборок.  
  
 [Образец построения C\/C\+\+](../Topic/C-C++%20Building%20Reference.md)  
 Содержит ссылки на справочные статьи о сборке программ на C\+\+, о параметрах компилятора и компоновщика, а также о различных средствах сборки.  
  
 [Настройка программ для 64\-разрядных систем](../build/configuring-programs-for-64-bit-visual-cpp.md)  
 Описывает настройку Visual Studio и командной строки для использования 64\-разрядного набора инструментов и создание программ для 64\-разрядных архитектур, а также различные затруднения при переносе кода на 64\-разрядные архитектуры.  
  
 [Настройка программ для процессоров ARM](../Topic/Configuring%20Programs%20for%20ARM%20Processors%20\(Visual%20C++\).md)  
 Описывает соглашения, используемые процессорами ARM, а также содержит обзор распространенных проблем миграции, возникающих при перемещении кода в архитектуры ARM.  
  
 [Настройка программ C\+\+ 11 для Windows XP](../build/configuring-programs-for-windows-xp.md)  
 Описывает настройку набора инструментов платформы для ориентации на разработку под Windows XP.  
  
## Связанные подразделы  
 [NIB: Samples Included in Visual C\+\+](http://msdn.microsoft.com/ru-ru/c9ec56b3-2bbd-49b4-8a4c-9ed4b78b7a84)  
 Содержит ссылки на примеры кода, иллюстрирующие возможности языка Visual C\+\+, а также поддерживаемых им библиотек и технологий.  
  
 [Построение приложений в Visual Studio](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)  
 Описывает систему сборки и средства Visual Studio.