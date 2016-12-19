---
title: "Использование взаимодействия языка C++ (неявный PInvoke) | Microsoft Docs"
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
  - ".NET [C++], перенос собственного C++ в"
  - "преобразуемые типы [C++]"
  - "COM-взаимодействие в C++"
  - "взаимодействие C++"
  - "C++, взаимодействие"
  - "интерфейсы COM [C++]"
  - "маршалинг данных [C++], C++ - функции взаимодействия"
  - "примеры [C++], взаимодействие"
  - "неявный вызов платформы"
  - "взаимодействие [C++], функции"
  - "взаимодействие [C++]"
  - "взаимодействие [C++], Неявный PInvoke"
  - "маршалинг [C++], C++ - функции взаимодействия"
  - "вызов неуправляемого кода [C++], примеры"
  - "вызов неуправляемого кода [C++], неявные"
  - "перенос [C++], перенос собственного C++ на платформу .NET"
  - "типы [C++], преобразуемый"
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование взаимодействия языка C++ (неявный PInvoke)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В отличие от других языков .NET Visual C\+\+ поддерживает функцию взаимодействия, которая позволяет управляемому и неуправляемому коду находиться в одном приложении и даже в одном файле \(вместе с директивами pragma [managed, unmanaged](../preprocessor/managed-unmanaged.md)\).  Это позволяет разработчикам Visual C\+\+ интегрировать функциональность .NET в существующие приложения Visual C\+\+, не затрагивая оставшуюся часть приложения.  
  
 Также можно вызывать неуправляемые функции из управляемой единицы компиляции с помощью [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 Неявный PInvoke полезен, если не нужно указывать способ маршалинга для параметров функции или любые другие подробности, которые можно указать при явном вызове DllImportAttribute.  
  
 Visual C\+\+ предоставляет два способа взаимодействия управляемых и неуправляемых функций:  
  
-   [Использование явного вызова Pinvoke в C\+\+ \(атрибут DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
 Явный PInvoke поддерживается платформой .NET Framework и доступен в большинстве языков .NET.  Но, как и намекает его имя, взаимодействия C\+\+ характерны для Visual C\+\+.  
  
## Взаимодействие C\+\+  
 Рекомендуется использовать взаимодействие C\+\+, а не явный вызов PInvoke, поскольку C\+\+ является более безопасен для типов, обычно менее трудоемок в реализации, более терпим при изменениях неуправляемого API и позволяет улучшать производительность, что представляется невозможным при явном вызове PInvoke.  Однако взаимодействия в языке C\+\+ невозможны, если неуправляемый исходный код недоступен или при компиляции с **\/clr:safe** \(дополнительные сведения см. в разделе [Чистый и проверяемый код](../dotnet/pure-and-verifiable-code-cpp-cli.md)\).  
  
## COM\-взаимодействие в C\+\+  
 Функции взаимодействия, поддерживаемые Visual C\+\+, имеют определенное преимущество над другими языками .NET при взаимодействии с компонентами COM.  Вместо нахождении в ограничениях .NET Framework [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md), таких как ограниченная поддержка типов данных или обязательное предоставление каждого члена интерфейса COM, взаимодействие C\+\+ позволяет обращаться к компонентам COM в любой момент и не требует отдельных сборок взаимодействий.  Для получения дополнительной информации см. [Using COM from .NET](http://msdn.microsoft.com/ru-ru/03976661-6278-4227-a6c1-3b3315502c15).  
  
## Преобразуемые типы  
 Неуправляемые API, которые используют простые, встроенные типы \(см. в разделе [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md)\), не требуют определенного кодирования, поскольку эти типы данных имеют такое же представление в памяти, но для более сложных типов данных необходим явный маршалинг.  Пример см. в разделе [Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).  
  
## Пример  
  
```  
// vcmcppv2_impl_dllimp.cpp  
// compile with: /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
// Implicit DLLImport specifying calling convention  
extern "C" int __stdcall MessageBeep(int);  
  
// explicit DLLImport needed here to use P/Invoke marshalling because  
// System::String ^ is not the type of the first parameter to printf  
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]  
// or just  
// [DllImport("msvcrt.dll")]  
int printf(System::String ^, ...);   
  
int main() {  
   // (string literals are System::String by default)  
   printf("Begin beep\n");  
   MessageBeep(100000);  
   printf("Done\n");  
}  
```  
  
  **Begin beep**  
**Готовый**   
## Содержание  
  
-   [Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C\+\+](../Topic/How%20to:%20Marshal%20ANSI%20Strings%20Using%20C++%20Interop.md)  
  
-   [Практическое руководство. Маршалирование строк Юникода с использованием взаимодействия C\+\+](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Практическое руководство. Маршалирование строк COM с помощью взаимодействия C\+\+](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
-   [Практическое руководство. Маршалирование структур с помощью взаимодействия C\+\+](../dotnet/how-to-marshal-structures-using-cpp-interop.md)  
  
-   [Практическое руководство. Упаковка и передача массивов с помощью взаимодействия C\+\+](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)  
  
-   [Практическое руководство. Маршалинг обратных вызовов и делегатов посредством C\+\+ Interop](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
-   [Практическое руководство. Упаковка встроенных указателей посредством взаимодействия C\+\+](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)  
  
-   [Практическое руководство. Доступ к символам объекта System::String](../dotnet/how-to-access-characters-in-a-system-string.md)  
  
-   [Практическое руководство. Преобразование строки char \* в массив System::Byte](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)  
  
-   [Практическое руководство. Преобразование типа System::String к wchar\_t\* или char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)  
  
-   [Практическое руководство. Преобразование строки System::String в стандартную строку](../dotnet/how-to-convert-system-string-to-standard-string.md)  
  
-   [Практическое руководство. Преобразование стандартной строки к типу System::String](../dotnet/how-to-convert-standard-string-to-system-string.md)  
  
-   [Практическое руководство. Получение указателя на массив байтов](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)  
  
-   [Практическое руководство. Загрузка неуправляемых ресурсов в массив байтов](../Topic/How%20to:%20Load%20Unmanaged%20Resources%20into%20a%20Byte%20Array.md)  
  
-   [Практическое руководство. Изменение ссылочного класса в собственной функции](../Topic/How%20to:%20Modify%20Reference%20Class%20in%20a%20Native%20Function.md)  
  
-   [Практическое руководство. Машинный код или среда CLR: определение цели созданного изображения](../Topic/How%20to:%20Determine%20if%20an%20Image%20is%20Native%20or%20CLR.md)  
  
-   [Практическое руководство. Добавление машинной библиотеки DLL в глобальный кэш сборок](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)  
  
-   [Практическое руководство. Сохранение ссылки на тип значения в собственном типе](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)  
  
-   [Практическое руководство. Хранение ссылки на объект в неуправляемой памяти](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)  
  
-   [Практическое руководство. Определение факта использования ключа \/clr при компиляции](../dotnet/how-to-detect-clr-compilation.md)  
  
-   [Практическое руководство. Преобразование между классами System::Guid и \_GUID](../Topic/How%20to:%20Convert%20Between%20System::Guid%20and%20_GUID.md)  
  
-   [Практическое руководство. Определение выходного параметра](../dotnet/how-to-specify-an-out-parameter.md)  
  
-   [Практическое руководство. Использование собственного типа в компиляции \/clr](../Topic/How%20to:%20Use%20a%20Native%20Type%20in%20a%20-clr%20Compilation.md)  
  
-   [Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md)  
  
-   [Практическое руководство. Создание программы\-оболочки для неуправляемого класса для использования в языке C\#](../Topic/How%20to:%20Wrap%20Native%20Class%20for%20Use%20by%20C%23.md)  
  
 Дополнительные сведения об использовании делегатов в сценарии взаимодействий см. в разделе [delegate](../windows/delegate-cpp-component-extensions.md).  
  
## См. также  
 [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)