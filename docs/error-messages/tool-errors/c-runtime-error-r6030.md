---
title: "Ошибка во время выполнения C R6030 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6030"
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
caps.latest.revision: 9
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка во время выполнения C R6030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

библиотека CRT не инициализирована  
  
 Эта ошибка возникает, если используется библиотека CRT, но код запуска CRT не был выполнен.  Эта ошибка может возникнуть в случае, если параметр компоновщика [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) используется для переопределения используемого по умолчанию адреса запуска; обычно это **mainCRTStartup** или **wmainCRTStartup** для консольного EXE\-приложения, **WinMainCRTStartup** или **wWinMainCRTStartup** для EXE\-приложения Windows, или же **\_DllMainCRTStartup** для библиотеки DLL.  Если при запуске не вызывается ни одна из вышеупомянутых функций, библиотека времени выполнения C не будет инициализирована.