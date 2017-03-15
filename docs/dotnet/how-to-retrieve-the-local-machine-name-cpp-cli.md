---
title: "Практическое руководство. Извлечение имени локального компьютера (C++/CLI) | Microsoft Docs"
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
  - "имя компьютера"
  - "имя компьютера, извлечение"
  - "machine_name, извлечение"
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Извлечение имени локального компьютера (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

На примере следующего кода демонстрируется метод извлечения имени локального компьютера \(имя компьютера, которое отображается в сети\).  Данную операцию можно выполнить с помощью строки <xref:System.Environment.MachineName%2A>, которая определяется в пространстве имени <xref:System.Environment>.  
  
## Пример  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## См. также  
 [Операции Windows](../dotnet/windows-operations-cpp-cli.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)