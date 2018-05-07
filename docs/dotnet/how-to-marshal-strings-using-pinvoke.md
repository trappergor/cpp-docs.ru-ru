---
title: 'Как: маршалирование строк с помощью PInvoke | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a377e7074e72693a1a63e392c64a6d60c5995b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Практическое руководство. Маршалирование строк с помощью PInvoke
В этом разделе объясняется, как собственных функций, принимающих строки в стиле C может вызываться с помощью строки CLR введите System::String, используя поддержку вызова платформы .NET Framework. Программистам Visual C++, рекомендуется использовать возможности взаимодействия C++ (когда это возможно), поскольку P/Invoke предоставляет мало времени компиляции сведений об ошибках, не является строго типизированным и может оказаться трудоемкой для реализации. Если неуправляемый интерфейс API упакован как библиотека DLL и исходный код недоступен, P/Invoke является единственным параметром, но см. в противном случае [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Управляемые и неуправляемые строки по-разному расположены в памяти, поэтому для передачи строк из управляемых в неуправляемые функции требует <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут, чтобы дать указание компилятору на необходимость вставки необходимые механизмы преобразования для маршалинга строковых данных правильно и безопасно.  
  
 Как и в случае с функциями, используйте только встроенные типы данных, <xref:System.Runtime.InteropServices.DllImportAttribute> используется для объявления управляемых точек входа в неуправляемые функции, но для передачи строк вместо объявления этих точек входа, принимающие строки в стиле C, дескриптор <xref:System.String> типа можно использовать вместо него. По этой причине, появляется компилятору на необходимость вставки кода, который выполняет необходимые преобразования. Для каждого аргумента функции в неуправляемой функции, которая принимает строку <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут должен использоваться для указания, что строковый объект необходимо маршалировать в неуправляемую функцию строка C-стиле.  
  
## <a name="example"></a>Пример  
 Следующий код состоит из неуправляемого и управляемого модуля. Неуправляемый модуль является библиотекой DLL, определяется функция TakesAString, принимающая строку ANSI C-стиле, в виде char *. Управляемый модуль является приложением командной строки, импортирующим функцию TakesAString, но определена как принимающая управляемого System.String вместо char\*. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Атрибут используется для указания того, каким образом следует маршалировать управляемая строка при вызове TakesAString.  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 Этот метод вызывает копию строки создаваться в неуправляемой куче, поэтому изменения, внесенные в строку с собственной функции не отражаются в управляемой копии строки.  
  
 Обратите внимание, что никакие компоненты библиотеки DLL не предоставляются в управляемый код с помощью традиционных #include. На самом деле DLL осуществляется во время выполнения, поэтому проблемы с функциями импортированы с `DllImport` во время компиляции не обнаруживаются.  
  
## <a name="see-also"></a>См. также  
 [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)