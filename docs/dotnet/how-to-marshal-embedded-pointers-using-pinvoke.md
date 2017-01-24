---
title: "Практическое руководство. Маршалинг внедренных указателей с помощью PInvoke | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "маршалинг данных [C++], встроенные указатели"
  - "встроенные указатели [C++]"
  - "взаимодействие [C++], встроенные указатели"
  - "маршалинг [C++], встроенные указатели"
  - "вызов неуправляемого кода [C++], встроенные указатели"
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалинг внедренных указателей с помощью PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функции, реализованные в неуправляемых библиотеках DLL, могут вызываться из управляемого кода с помощью вызова неуправляемого кода P\/Invoke.  Если исходный код библиотеки DLL недоступен, вызов P\/Invoke является единственным вариантом обеспечения взаимодействия.  В отличие от других языков .NET в Visual C\+\+ предусматривается альтернатива вызову P\/Invoke.  Дополнительные сведения см. в разделах [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md) и [Практическое руководство. Упаковка встроенных указателей посредством взаимодействия C\+\+](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
## Пример  
 Структура передачи данных в машинный код требует, чтобы была создана управляемая структура с параметрами компоновки данных эквивалентными машинной структуре.  Однако структуры, содержащие указатели, требуют особой обработки.  Для каждого внедренного указателя в машинной структуре управляемая версия структуры должна содержать экземпляр типа <xref:System.IntPtr>.  Также память должна явно выделяться, инициализироваться и освобождаться с помощью методов <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A> и <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A>.  
  
 В следующем примере кода представлены неуправляемый и управляемый модули.  Неуправляемый модуль является библиотекой DLL, определяющей функцию, которая принимает структуру по имени ListString, которая содержит указатель, и функцию по имени TakesListStruct.  Управляемый модуль является приложением командной строки, импортирующим функцию TakesListStruct, и содержит структуру с именем MListStruct эквивалентную машинной структуре ListStruct за исключением того, что двойная звездочка \(\*\*\) заменена на <xref:System.IntPtr>.  Перед вызовом TakesListStruct основная функция выделяет и инициализирует память, на которую ссылается данное поле.  
  
 Управляемый модуль компилируется с параметром \/clr, также возможна компиляция с \/clr:pure.  
  
```  
// TraditionalDll6.cpp  
// compile with: /EHsc /LD  
#include <stdio.h>  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct ListStruct {  
   int count;  
   double* item;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API void TakesListStruct(ListStruct);  
}  
  
void TakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
```  
  
```  
// EmbeddedPointerMarshalling.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MListStruct {  
   int count;  
   IntPtr item;  
};  
  
value struct TraditionalDLL {  
    [DllImport("TraditionalDLL6.dll")]  
   static public void TakesListStruct(MListStruct);  
};  
  
int main() {  
   array<double>^ parray = gcnew array<double>(10);  
   Console::WriteLine("[managed] count = {0}", parray->Length);  
  
   Random^ r = gcnew Random();  
   for (int i=0; i<parray->Length; i++) {  
      parray[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);  
   }  
  
   int size = Marshal::SizeOf(double::typeid);  
   MListStruct list;  
   list.count = parray->Length;  
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);  
  
   for (int i=0; i<parray->Length; i++) {  
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);  
      Marshal::StructureToPtr(parray[i], t, false);  
   }  
  
   TraditionalDLL::TakesListStruct( list );  
   Marshal::FreeCoTaskMem(list.item);  
}  
```  
  
 Обратите внимание, что в управляемом коде никакие компоненты библиотеки DLL не предоставляются с помощью стандартной директивы \#include.  Фактически доступ к библиотеке DLL происходит только во время выполнения, поэтому проблемы с функциями, импортируемыми с помощью <xref:System.Runtime.InteropServices.DllImportAttribute> не обнаруживаются во время компиляции.  
  
## См. также  
 [Использование явного вызова Pinvoke в C\+\+ \(атрибут DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)