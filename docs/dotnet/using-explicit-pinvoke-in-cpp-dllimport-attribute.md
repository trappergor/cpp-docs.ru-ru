---
title: "Использование явного вызова Pinvoke в C++ (атрибут DllImport) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "взаимодействие C++, вызов неуправляемого кода"
  - "маршалинг данных [C++], вызов неуправляемого кода"
  - "взаимодействие [C++], вызов неуправляемого кода"
  - "маршалинг [C++], вызов неуправляемого кода"
  - "вызов неуправляемого кода [C++], маршалинг (C++)"
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование явного вызова Pinvoke в C++ (атрибут DllImport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Платформа .NET Framework предоставляет функции вызова неуправляемого кода \(или PInvoke\) с помощью атрибута `Dllimport`, что позволяет управляемым приложениям вызывать неуправляемые функции, поставляемые в библиотеках DLL.  Явный вызов PInvoke необходим в случаях, когда неуправляемые API\-интерфейсы упаковываются как библиотеки DLL и исходный код недоступен.  Например, вызов Pinvoke необходим для вызова функций Win32.  В остальных случаях следует использовать неявный вызов P{Invoke. Дополнительные сведения см. в разделе [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Вызов PInvoke выполняется с помощью атрибута <xref:System.Runtime.InteropServices.DllImportAttribute>.  Этот атрибут принимает значение имени библиотеки DLL в качестве своего первого аргумента и помещается перед объявлением функции для каждой используемой в библиотеке DLL точки входа.  Подпись функции должна соответствовать имени функции, экспортируемой из библиотеки DLL \(однако часть преобразования типов можно выполнить неявно, объявив управляемые типы с помощью атрибута `DllImport`\).  
  
 Это приведет к созданию управляемой точки входа для каждой собственной функции библиотеки DLL, содержащей необходимый код перехода \(или преобразователь\) и простые преобразования данных.  Затем можно использовать эти точки входа для вызова управляемых функций из библиотеки DLL.  Код, вставленный в модуль в результате вызова Pinvoke, является полностью управляемым, а явный вызов Pinvoke поддерживается для компиляции **\/clr**, **\/clr:pure** и **\/clr:safe**.  Для получения дополнительной информации см. [Чистый и проверяемый код](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## В этом подразделе  
  
-   [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалирование строк с помощью PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалирование структур с помощью PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг массивов с помощью службы PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Практическое руководство. Указатели функций маршалирования, использующие PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг внедренных указателей с помощью PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## См. также  
 [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)