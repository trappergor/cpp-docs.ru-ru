---
title: "Домены приложений и Visual C++ | Microsoft Docs"
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
  - "/clr - параметр компилятора [C++], домены приложений"
  - "домены приложений [C++], C++"
  - "взаимодействие [C++], домены приложений"
  - "взаимодействие [C++], домены приложений"
  - "смешанные сборки [C++], домены приложений"
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Домены приложений и Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если имеется установленная виртуальная функция `__clrcall`, файл vtable используется для домена приложения \(appdomain\).  При создании объекта в пределах appdomain можно вызвать только виртуальную функцию.  Все функции, определенные в компиляторах как **\/clr:pure**, используют соглашение о вызове `__clrcall`.  Таким образом, все файлы vtable, определенные в компиляторах как единицы компиляции **\/clr:pure** используются в appdomain.  В смешанном режиме \(**\/clr**\) каждый процесс имеет свой файл vtable при отсутствии виртуальных функций `__clrcall`.  
  
 Дополнительные сведения см. в следующем разделе.  
  
-   [appdomain](../Topic/appdomain.md)  
  
-   [\_\_clrcall](../cpp/clrcall.md)  
  
-   [Практическое руководство. Миграция в \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [процесс](../cpp/process.md)  
  
## См. также  
 [Смешанные \(собственные и управляемые\) сборки](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)