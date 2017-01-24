---
title: "Общие сведения о маршалировании в C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshaling"
  - "marshalling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Библиотека поддержки C++, маршалинг"
  - "маршалинг, сведения о маршалинге"
  - "Visual C++, маршалинг"
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Общие сведения о маршалировании в C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В смешанном режиме, иногда требуется маршалинг свои данные и размещения между управляемыми.  в [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] введена библиотеки маршалинга для облегчения маршалинг и преобразования данных в простом способом.  
  
 Можно использовать библиотеку маршалинга с параметрами или без [Класс marshal\_context](../dotnet/marshal-context-class.md).  Некоторые преобразования требуется контекста.  Другие преобразования можно реализовать с помощью функции [marshal\_as](../dotnet/marshal-as.md).  В следующей таблице перечислены поддерживаемые текущие преобразования, требуется ли они контекста и какой маршала файл, должен включать:  
  
|От типа|Печать|Метод Marshal|Включите файл|  
|-------------|------------|-------------------|-------------------|  
|System::String^|const char \*|marshal\_context|marshal.h|  
|const char \*|System::String^|marshal\_as|marshal.h|  
|char \*|System::String^|marshal\_as|marshal.h|  
|System::String^|const wchar\_t\*|marshal\_context|marshal.h|  
|const wchar\_t \*|System::String^|marshal\_as|marshal.h|  
|wchar\_t \*|System::String^|marshal\_as|marshal.h|  
|System::IntPtr|HANDLE|marshal\_as|marshal\_windows.h|  
|HANDLE|System::IntPtr|marshal\_as|marshal\_windows.h|  
|System::String^|BSTR|marshal\_context|marshal\_windows.h|  
|BSTR|System::String^|marshal\_as|marshal.h|  
|System::String^|bstr\_t|marshal\_as|marshal\_windows.h|  
|bstr\_t|System::String^|marshal\_as|marshal\_windows.h|  
|System::String^|std::string|marshal\_as|marshal\_cppstd.h|  
|std::string|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|std::wstring|marshal\_as|marshal\_cppstd.h|  
|std::wstring|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|CStringT\<char\>|marshal\_as|marshal\_atl.h|  
|CStringT\<char\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CStringT\<wchar\_t\>|marshal\_as|marshal\_atl.h|  
|CStringT\<wchar\_t\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CComBSTR|marshal\_as|marshal\_atl.h|  
|CComBSTR|System::String^|marshal\_as|marshal\_atl.h|  
  
 Маршалинг требуется контекст только при маршалируете из управляемой в собственные типы данных и собственный тип, в который требуется выполнить преобразование не имеет деструктор автоматического очистить.  Контекст маршалинга удаляет выбранный собственный тип данных в деструкторе его.  Поэтому преобразования, требующих контекста, допустимы только до тех пор, пока контекст не удаляется.  Для сохранения всех маршалированные значений необходимо скопировать значения к пользовательским переменным.  
  
> [!NOTE]
>  Если имеются внедренные `NULL` в строку, не гарантирован результат маршалинг строка.  Внедренный `NULL` может привести к строке быть усеченным или они могут быть сохранены.  
  
 Заголовки библиотеки маршалинга расположены в папке включение в подкаталоге msclr.  В этом примере показано, как включить каталог msclr в объявлении заголовка включение:  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 Библиотека маршалинга может быть расширена для добавления собственных типов маршалинга.  Дополнительные сведения о расширенном библиотеки маршалинга см. в разделе [Практическое руководство. Расширение библиотеки маршалинга](../dotnet/how-to-extend-the-marshaling-library.md).  
  
 В более ранних версиях можно было маршалинг данных с помощью [Вызов неуправляемого кода](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md).  Дополнительные сведения о `PInvoke` см. в разделе [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md).  
  
## См. также  
 [Библиотека поддержки C\+\+](../dotnet/cpp-support-library.md)   
 [Практическое руководство. Расширение библиотеки маршалинга](../dotnet/how-to-extend-the-marshaling-library.md)