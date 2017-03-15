---
title: "Практическое руководство. Использование регулярных выражений для простых совпадений (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "IsMatch - метод"
  - "регулярные выражения [C++], простое соответствие"
  - "поиск, точные совпадения подстрок"
  - "строки [C++], точные совпадения подстрок"
  - "подстроки, простые соответствия"
ms.assetid: 4661f6f3-0f6d-48f2-abe4-cb4770bf9bd5
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование регулярных выражений для простых совпадений (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода используются регулярные выражения для поиска совпадающих подстрок.  Поиск выполняется с помощью статического метода <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>, который в качестве входных значений принимает две строки.  Первая представляет собой строку, в которой выполняется поиск, а вторая — искомый шаблон.  
  
## Пример  
  
```  
// regex_simple.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ sentence =   
   {  
      "cow over the moon",  
      "Betsy the Cow",  
      "cowering in the corner",  
      "no match here"  
   };  
  
   String^ matchStr = "cow";  
   for (int i=0; i<sentence->Length; i++)  
   {  
      Console::Write( "{0,24}", sentence[i] );  
      if ( Regex::IsMatch( sentence[i], matchStr,  
                     RegexOptions::IgnoreCase ) )  
         Console::WriteLine("  (match for '{0}' found)", matchStr);  
      else  
         Console::WriteLine("");  
   }  
   return 0;  
}  
```  
  
## См. также  
 [Регулярные выражения в .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)