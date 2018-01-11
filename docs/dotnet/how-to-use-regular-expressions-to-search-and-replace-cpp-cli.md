---
title: "Как: использование регулярных выражений для поиска и замены (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- search and replace
- Replace method
- regular expressions [C++], search and replace
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f66df471d66a82a565fc5c072757664567d1f25c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-regular-expressions-to-search-and-replace-ccli"></a>Практическое руководство. Использование регулярных выражений для выполнения поиска и замены (C++/CLI)
В следующем примере кода показано, как класс регулярного выражения <xref:System.Text.RegularExpressions.Regex> можно использовать для выполнения поиска и замены. Это делается с <xref:System.Text.RegularExpressions.Regex.Replace%2A> метод. Используемая версия принимает две строки в качестве входных данных: строка для изменения и строки для вставки вместо разделов (если таковые имеются), соответствующих шаблону, заданному для <xref:System.Text.RegularExpressions.Regex> объекта.  
  
 Данный код заменяет все цифры в строку с символами подчеркивания (_), а затем заменяет их на пустую строку, фактически удаляя их. Того же результата можно добиться за один шаг, но здесь используются два шага для демонстрационных целей.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения в .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)