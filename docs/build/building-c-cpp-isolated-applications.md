---
title: "Построение изолированных приложений C/C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "изолированные приложения [C++]"
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Построение изолированных приложений C/C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Изолированное приложение зависит только от параллельных сборок и привязывается к ним посредством манифеста.  Чтобы упростить последующее обслуживание приложения, рекомендуется сделать его полностью изолированным, однако это не обязательно для его выполнения в Windows.  Дополнительные сведения о преимуществах полностью изолированных приложений см. в разделе [Изолированные приложения](http://msdn.microsoft.com/library/aa375190).  
  
 При построении приложений C\/C\+\+ в машинном коде с помощью Visual C\+\+ в системе проектов Visual Studio по умолчанию создается файл манифеста, в котором описываются зависимости приложения от библиотек Visual C\+\+.  Если в этом файле описаны все зависимости приложения, при повторном построении такого приложения в Visual Studio оно становится полностью изолированным.  Если во время выполнения в приложении используются другие библиотеки, возможно, потребуется их повторное построение в качестве параллельных сборок \(см. раздел [Построение параллельных сборок C\/C\+\+](../build/building-c-cpp-side-by-side-assemblies.md)\).  
  
## См. также  
 [Основные понятия, связанные с изолированными приложениями и параллельными сборками](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Построение изолированных приложений и параллельных сборок C\/C\+\+](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)