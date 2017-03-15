---
title: "Практическое руководство. Использование регулярных выражений для выполнения поиска и замены (C++/CLI) | Microsoft Docs"
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
  - "регулярные выражения [C++], поиск и замена"
  - "Replace - метод"
  - "поиск и замена"
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование регулярных выражений для выполнения поиска и замены (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода показаны способы использования класса регулярных выражений <xref:System.Text.RegularExpressions.Regex> для выполнения поиска и замены.  Для этого используется метод <xref:System.Text.RegularExpressions.Regex.Replace%2A>.  Используемая версия принимает в качестве входных данных две строки: строку, подлежащую изменению, и строку, подлежащую вставке вместо разделов, соответствующих шаблону, предоставленному объекту <xref:System.Text.RegularExpressions.Regex>, если таковые существуют.  
  
 Этот код заменяет все цифры в строке на символ подчеркивания \(\_\), а затем заменяет их на пустую строку, фактически удаляя их.  Того же результата можно добиться и одним действием. Два действия показаны здесь только в демонстрационных целях.  
  
## Пример  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## См. также  
 [Регулярные выражения в .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)