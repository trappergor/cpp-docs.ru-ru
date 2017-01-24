---
title: "Практическое руководство. Определение начала процесса завершения работы (C++/CLI) | Microsoft Docs"
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
  - "платформа .NET Framework, завершение работы"
  - "приложения [C++], завершение работы"
  - "завершение работы"
  - "завершение"
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Определение начала процесса завершения работы (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующий пример кода показывает, как определить, завершено ли в данный момент приложение или .NET Framework.  Данная возможность полезна при доступе к статическим элементам в платформе .NET Framework, т.к. в ходе завершения работы функционирование данных конструкторов завершается системой и не могут использоваться.  Чтоб избежать потенциальных ошибок, связанных с доступом к данным элементам, необходимо сперва проверить значение свойства <xref:System.Environment.HasShutdownStarted%2A>.  
  
## Пример  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## См. также  
 [Операции Windows](../dotnet/windows-operations-cpp-cli.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)