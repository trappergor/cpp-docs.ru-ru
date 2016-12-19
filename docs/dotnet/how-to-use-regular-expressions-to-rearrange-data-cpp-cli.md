---
title: "Практическое руководство. Использование регулярных выражений для изменения порядка данных (C++/CLI) | Microsoft Docs"
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
  - "данные [C++], переупорядочение"
  - "регулярные выражения [C++], перегруппировка данных"
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование регулярных выражений для изменения порядка данных (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

На следующем примере кода демонстрируется использование поддержки регулярных выражений на базе платформы .NET Framework во время изменения порядка или формата данных.  В следующем примере кода используются классы <xref:System.Text.RegularExpressions.Regex> и <xref:System.Text.RegularExpressions.Match>, которые извлекают первые и последние имена элементов строки и отображают их в обратном порядке.  
  
 Класс <xref:System.Text.RegularExpressions.Regex> используется для построения регулярного выражения, которое характеризует текущий формат данных.  Два имени разделяются запятой и можно использовать любое количество пробелов вокруг запятой.  Затем применяется метод <xref:System.Text.RegularExpressions.Match>, который позволяет анализировать отдельно каждую строку.  При удачно выполненном анализе первые и последние имена извлекаются из объекта <xref:System.Text.RegularExpressions.Match> для отображения.  
  
## Пример  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## См. также  
 [Регулярные выражения в .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)