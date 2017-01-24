---
title: "Автоматизация в библиотеке DLL | Microsoft Docs"
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
  - "автоматизация [C++], библиотеки DLL"
  - "DLL-библиотеки [C++], автоматизация"
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Автоматизация в библиотеке DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Когда в мастере MFC DLL устанавливается параметр "Автоматизация", мастер выполняет следующие действия:  
  
-   Создает начальный файл на языке описания объектов \(ODL\).  
  
-   Добавляет в заголовочный файл STDAFX.h директиву \#include для файла Afxole.h.  
  
-   Реализует функцию `DllGetClassObject`, которая вызывает функцию **AfxDllGetClassObject**.  
  
-   Реализует функцию `DllCanUnloadNow`, которая вызывает функцию **AfxDllCanUnloadNow**.  
  
-   Реализует функцию `DllRegisterServer`, которая вызывает функцию [COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md).  
  
## Дополнительные сведения  
  
-   [Серверы автоматизации](../mfc/automation-servers.md)  
  
## См. также  
 [DLL в Visual C\+\+](../build/dlls-in-visual-cpp.md)