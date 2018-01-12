---
title: "Использование явного вызова PInvoke в C++ (атрибут DllImport) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d05c88167629bcb6bf86dc600afde0ea3162064f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>Использование явного вызова Pinvoke в C++ (атрибут DllImport)
.NET Framework предоставляет функции вызова неуправляемого кода (или PInvoke) с `Dllimport` атрибут позволяет управляемым приложениям вызывать неуправляемые функции, поставляемые в библиотеках DLL. Явный вызов PInvoke необходим для ситуациях, когда неуправляемый API-интерфейсы упаковываются как библиотеки DLL и исходный код недоступен. Например, вызов функции Win32 требует PInvoke. В противном случае используйте неявные P {Invoke см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) для получения дополнительной информации.  
  
 Вызов PInvoke выполняется с помощью <xref:System.Runtime.InteropServices.DllImportAttribute>. Этот атрибут, который принимает имя библиотеки DLL в качестве своего первого аргумента, помещается перед объявлением функции для каждой точки входа библиотеки DLL, которая будет использоваться. Сигнатура функции должно соответствовать имени функции, экспортируемой библиотекой DLL (но некоторые преобразование типа может быть выполнено неявно путем определения `DllImport` объявления с точки зрения управляемых типов.)  
  
 Результатом является управляемую точку входа для каждой собственной функции библиотеки DLL, содержащую необходимый код перехода (или преобразователь) и простые преобразования данных. Управляемые функции можно вызывать через эти точки входа библиотеки DLL. Код, вставленный в модуль в результате вызова PInvoke, является полностью управляемым, а явный вызов PInvoke поддерживается для **/CLR**, **/CLR: pure**, и **/CLR: safe** компиляций. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать. Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="in-this-section"></a>В этом разделе  
  
-   [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг строк с помощью PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг структур с помощью PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг массивов с помощью PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Практическое руководство. Указатели функций маршалинга, использующие PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг внедренных указателей с помощью PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## <a name="see-also"></a>См. также  
 [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)