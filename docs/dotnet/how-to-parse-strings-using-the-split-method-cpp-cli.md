---
title: "Практическое руководство. Анализ строк с помощью метода разделения (C++/CLI) | Microsoft Docs"
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
  - "примеры [C++], строки"
  - "разбор строк [C++]"
  - "регулярные выражения [C++], разбор строк"
  - "Split - метод, разбор строк"
  - "строки [C++], синтаксический разбор"
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Анализ строк с помощью метода разделения (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода демонстрируется извлечение каждого слова из строки при помощи метода <xref:System.String.Split%2A?displayProperty=fullName>.  Строка, содержащая множество различных типов описаний слов, создается и затем анализируется путем вызова метода <xref:System.String.Split%2A> со списком описаний.  Затем отдельно отображается каждое слово предложения.  
  
## Пример  
  
```  
// regex_split.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String^ delimStr = " ,.:\t";  
   Console::WriteLine( "delimiter : '{0}'", delimStr );  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ words;  
   String^ line = "one\ttwo three:four,five six seven";  
  
   Console::WriteLine( "text : '{0}'", line );  
   words = line->Split( delimiter );  
   Console::WriteLine( "Number of Words : {0}", words->Length );  
   for (int word=0; word<words->Length; word++)  
      Console::WriteLine( "{0}", words[word] );  
  
   return 0;  
}  
```  
  
## См. также  
 [Регулярные выражения в .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)