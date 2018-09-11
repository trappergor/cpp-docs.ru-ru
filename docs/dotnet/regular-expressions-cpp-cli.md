---
title: Регулярные выражения (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular expressions [C++]
- .NET Framework [C++], regular expressions
- regular expressions [C++], about regular expressions
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
- substrings, simple matches
- searching, exact substring matches
- strings [C++], exact substring matching
- regular expressions [C++], simple matching
- IsMatch method
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
- regular expressions [C++], rearranging data
- data [C++], rearranging
- search and replace
- Replace method
- regular expressions [C++], search and replace
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 838bab49-0dbc-4089-a604-ef146269ef5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8732b7da770625377c556f26e98c0a5f2e5073b6
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895244"
---
# <a name="regular-expressions-ccli"></a>Регулярные выражения (C++/CLI)

Демонстрирует использование классов регулярных выражений в .NET Framework различных операций со строками.

В следующих разделах описывается использование платформы .NET Framework <xref:System.Text.RegularExpressions> пространства имен (и в одном из случаев <xref:System.String.Split%2A?displayProperty=fullName> метод) для поиска, анализировать и изменять строки.

## <a name="parse_regex"></a> Анализ строк с помощью регулярных выражений

В следующем примере кода демонстрируется простой анализ строки с помощью <xref:System.Text.RegularExpressions.Regex> в класс <xref:System.Text.RegularExpressions?displayProperty=fullName> пространства имен. Строка, содержащая несколько типов разделителей слов создается. Строка анализируется с использованием <xref:System.Text.RegularExpressions.Regex> класс в сочетании с <xref:System.Text.RegularExpressions.Match> класса. Затем каждое слово в предложении отображается отдельно.

### <a name="example"></a>Пример

```cpp
// regex_parse.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main( )  
{
   int words = 0;
   String^ pattern = "[a-zA-Z]*";
   Console::WriteLine( "pattern : '{0}'", pattern );
   Regex^ regex = gcnew Regex( pattern );

   String^ line = "one\ttwo three:four,five six  seven";
   Console::WriteLine( "text : '{0}'", line );
   for( Match^ match = regex->Match( line );
        match->Success; match = match->NextMatch( ) )
   {
      if( match->Value->Length > 0 )  
      {
         words++;
         Console::WriteLine( "{0}", match->Value );
      }
   }
   Console::WriteLine( "Number of Words : {0}", words );

   return 0;
}
```  

## <a name="parse_split"></a> Анализ строк с помощью метода разделения

В следующем примере кода показано использование <xref:System.String.Split%2A?displayProperty=fullName> метод для извлечения каждого слова из строки. Строка, содержащая несколько типов разделителей слов создается и затем анализируется путем вызова метода <xref:System.String.Split%2A> со списком описаний. Затем каждое слово в предложении отображается отдельно.

### <a name="example"></a>Пример

```cpp
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

## <a name="regex_simple"></a> Использование регулярных выражений для простых совпадений

В следующем примере кода используются регулярные выражения для поиска совпадающих подстрок. Поиск выполняется статическим <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> метод, который принимает в качестве входных данных две строки. Первая строка для поиска, а второй — шаблон для поиска.

### <a name="example"></a>Пример

```cpp
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

## <a name="regex_extract"></a> Использование регулярных выражений для извлечения полей данных

В следующем примере кода показано использование регулярных выражений для извлечения данных из форматируемой строки. В следующем примере кода используется <xref:System.Text.RegularExpressions.Regex> класс, чтобы указать шаблон, который соответствует адресу электронной почты. Этот шаблон включены идентификаторы полей, которые можно использовать для получения имени пользователя и имени узла каждого адреса электронной почты. <xref:System.Text.RegularExpressions.Match> Класс используется для выполнения соответствия шаблона. Если адрес электронной почты допустим, имя пользователя и имена узлов извлекаются и отображаются.

### <a name="example"></a>Пример

```cpp
// Regex_extract.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()  
{
    array<String^>^ address=
    {
        "jay@southridgevideo.com",
        "barry@adatum.com",
        "treyresearch.net",
        "karen@proseware.com"
    };

    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");

    for (int i=0; i<address->Length; i++)  
    {
        Match^ m = emailregex->Match( address[i] );
        Console::Write("\n{0,25}", address[i]);

        if ( m->Success )   
        {
            Console::Write("   User='{0}'",
            m->Groups["user"]->Value);
            Console::Write("   Host='{0}'",
            m->Groups["host"]->Value);
        }
        else
            Console::Write("   (invalid email address)");
        }

    Console::WriteLine("");
    return 0;
}
```  

## <a name="regex_rearrange"></a> Использование регулярных выражений для изменения порядка данных

В следующем примере кода показано, как поддержка регулярных выражений .NET Framework может использоваться для изменения порядка или формата данных. В следующем примере кода используется <xref:System.Text.RegularExpressions.Regex> и <xref:System.Text.RegularExpressions.Match> классы, позволяющие извлечь имена и фамилии из строки и затем отобразить эти имена элементов в обратном порядке.

<xref:System.Text.RegularExpressions.Regex> Класс используется для создания регулярного выражения, который описывает текущий формат данных. Два имени предполагается, что должны быть разделены запятыми и можно использовать любое количество пробелов вокруг запятой. <xref:System.Text.RegularExpressions.Match> Метод используется для анализа каждой строки. В случае успешного выполнения имена и фамилии извлекаются из <xref:System.Text.RegularExpressions.Match> объекта и отображается.

### <a name="example"></a>Пример

```cpp
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

## <a name="regex_search"></a> Использование регулярных выражений для поиска и замены

В следующем примере кода показано, как класс регулярного выражения <xref:System.Text.RegularExpressions.Regex> может использоваться для выполнения поиска и замены. Это делается с помощью <xref:System.Text.RegularExpressions.Regex.Replace%2A> метод. Используемая версия принимает две строки в качестве входных данных: строка для изменения и строку для вставки вместо разделов (если таковые имеются), соответствующих шаблону, присвоенный <xref:System.Text.RegularExpressions.Regex> объекта.

Этот код заменяет все цифры в строку с символами подчеркивания (_) и затем заменяет их на пустую строку, фактически удаляя их. Тот же эффект достигается за один шаг, но здесь используются два шага для демонстрационных целей.

### <a name="example"></a>Пример

```cpp
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

## <a name="regex_validate"></a> Использование регулярных выражений для проверки форматирования данных

В следующем примере кода показано использование регулярных выражений для проверки формата строки. В следующем примере кода строка должна содержать допустимый номер телефона. В следующем примере кода используется строка «\d{3}-\d{3}-\d{4}"для указания, что каждое поле представляет допустимый номер телефона. В строке «d» обозначает цифру, а аргумент после каждое «d» Указывает количество цифр, которые должны присутствовать. В этом случае номер необходим для разделенных знаком тире.

### <a name="example"></a>Пример

```cpp
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

## <a name="related-sections"></a>Связанные разделы

[Регулярные выражения в .NET Framework](/dotnet/standard/base-types/regular-expressions)  

## <a name="see-also"></a>См. также

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)