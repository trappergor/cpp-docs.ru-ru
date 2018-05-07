---
title: Использование регулярных выражений для проверки форматирования (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 59a553ac2d58f9304fce3961aa8212c33b26643a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-regular-expressions-to-validate-data-formatting-ccli"></a>Практическое руководство. Использование регулярных выражений для проверки форматирования данных (C++/CLI)
В следующем примере кода показано использование регулярных выражений для проверки формата строки. В следующем примере строка должна содержать допустимый номер телефона. В следующем примере кода используется строка «\d{3}-\d{3}-\d{4}», чтобы указать, что каждое поле представляет допустимый номер телефона. В строке «d» обозначает цифру, а аргумент после «d» Указывает количество цифр, которые должны быть созданы. В этом случае номер требуется должны разделяться знаком тире.  
  
## <a name="example"></a>Пример  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения в .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)