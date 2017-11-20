---
title: "Общие сведения о маршалировании в C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
dev_langs: C++
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 384c8bac652e16a4f66a82ee7e4dbb5cc92fd32b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="overview-of-marshaling-in-c"></a>Общие сведения о маршалировании в C++
В смешанном режиме иногда необходимо выполнять маршалинг данных между неуправляемыми и управляемыми типами. [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)]представленные библиотеке маршалинга для упаковки и преобразования данных в простой способ.  
  
 Библиотека маршалинга можно использовать с или без [класс marshal_context](../dotnet/marshal-context-class.md). Некоторые преобразования требуется контекст. Другие преобразования может осуществляться с помощью [marshal_as](../dotnet/marshal-as.md) функции. В следующей таблице перечислены текущего преобразования, поддерживаемые, требуется ли контекст и какой файл маршалирование необходимо включить:  
  
|Из типа|Для ввода|Метод маршалинга|Включаемый файл|  
|---------------|-------------|--------------------|------------------|  
|System::String ^|const char *|marshal_context|Marshal.h|  
|const char *|System::String ^|marshal_as|Marshal.h|  
|char *|System::String ^|marshal_as|Marshal.h|  
|System::String ^|const wchar_t*|marshal_context|Marshal.h|  
|const wchar_t *|System::String ^|marshal_as|Marshal.h|  
|wchar_t *|System::String ^|marshal_as|Marshal.h|  
|System::IntPtr|HANDLE|marshal_as|marshal_windows.h|  
|HANDLE|System::IntPtr|marshal_as|marshal_windows.h|  
|System::String ^|BSTR|marshal_context|marshal_windows.h|  
|BSTR|System::String ^|marshal_as|Marshal.h|  
|System::String ^|bstr_t|marshal_as|marshal_windows.h|  
|bstr_t|System::String ^|marshal_as|marshal_windows.h|  
|System::String ^|std::String|marshal_as|marshal_cppstd.h|  
|std::String|System::String ^|marshal_as|marshal_cppstd.h|  
|System::String ^|std::wstring|marshal_as|marshal_cppstd.h|  
|std::wstring|System::String ^|marshal_as|marshal_cppstd.h|  
|System::String ^|CStringT\<char >|marshal_as|marshal_atl.h|  
|CStringT\<char >|System::String ^|marshal_as|marshal_atl.h|  
|System::String ^|CStringT < wchar_t >|marshal_as|marshal_atl.h|  
|CStringT < wchar_t >|System::String ^|marshal_as|marshal_atl.h|  
|System::String ^|CComBSTR|marshal_as|marshal_atl.h|  
|CComBSTR|System::String ^|marshal_as|marshal_atl.h|  
  
 Требуется контекст маршалинга, только когда маршалинга из управляемого в машинный код данных типов и собственный тип, который необходимо преобразовать имеет деструктор для автоматической очистки. Контекст маршалинга удаляет выделенный собственного типа данных в деструкторе. Таким образом преобразования, которым требуется контекст допустимы только в том случае, пока контекст не будет удален. Чтобы сохранить все упакованные значения, необходимо скопировать значения собственные переменные.  
  
> [!NOTE]
>  Если с внедренными `NULL`s в строке результат маршалинг строки не гарантируется. Встроенный `NULL`, может привести к строке, будут усечены, или они могут сохраняться.  
  
 Заголовки библиотеки маршалинга расположены в папке include в подкаталоге msclr. В этом примере показано, как включить каталог msclr в объявлении заголовок include:  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 Библиотека маршалинга является расширяемым, которые можно добавлять собственные маршалинга типов. Дополнительные сведения о расширении библиотеке маршалинга см. в разделе [как: расширение библиотеки маршалинга](../dotnet/how-to-extend-the-marshaling-library.md).  
  
 В более ранних версиях необходимо маршалинг данных с помощью [неуправляемого](/dotnet/framework/interop/consuming-unmanaged-dll-functions). Дополнительные сведения о `PInvoke`, в разделе [вызов собственных функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md).  
  
## <a name="see-also"></a>См. также  
 [Библиотека поддержки C++](../dotnet/cpp-support-library.md)   
 [Практическое руководство. Расширение библиотеки маршалинга](../dotnet/how-to-extend-the-marshaling-library.md)