---
title: "Практическое руководство. Определение интерактивного состояния пользователя (C++/CLI) | Microsoft Docs"
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
  - "интерактивное состояние пользователя"
  - "Visual C++, интерактивное состояние пользователя"
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Определение интерактивного состояния пользователя (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представленный ниже пример кода демонстрирует, как определить, выполняется ли код в контексте интерактивного взаимодействия с пользователем.  Если <xref:System.Environment.UserInteractive%2A> имеет значение "false", то код выполняется как служебный процесс или изнутри веб\-приложения. В этом случае не следует предпринимать попытку взаимодействия с пользователем.  
  
## Пример  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## См. также  
 [Операции Windows](../dotnet/windows-operations-cpp-cli.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)