---
title: "Как: маршалинг встроенных указателей посредством PInvoke | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c8f6716a11919c300dc3153ca678767503a35088
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>Практическое руководство. Маршалинг внедренных указателей с помощью PInvoke
Функции, реализованные в неуправляемых библиотек DLL может вызываться из управляемого кода с помощью функциональной возможности вызова неуправляемого кода (P/Invoke). Если исходный код для библиотеки DLL недоступен, P/Invoke является единственным вариантом обеспечения взаимодействия. Однако в отличие от других языков .NET, Visual C++ предоставляет альтернативы P/Invoke. Дополнительные сведения см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) и [как: маршалинг внедренных указателей с помощью взаимодействия C++](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
## <a name="example"></a>Пример  
 Передача структур в машинный код требует, создается управляемая структура с параметрами компоновки данных эквивалентными машинной структуре. Однако структуры, содержащие указатели требуют специальной обработки. Для каждого внедренного указателя в машинной структуре управляемую версию структуры должна содержать экземпляр <xref:System.IntPtr> типа. Кроме того, память для этих экземпляров, должен быть явно выделен, инициализации и освобождены с помощью <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>, и <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> методы.  
  
 Следующий код состоит из неуправляемый и управляемый модуль. Неуправляемый модуль является библиотекой DLL, определяющей функцию, которая принимает структуру ListString, которая содержит указатель и функция, вызываемая TakesListStruct. Управляемый модуль является приложением командной строки, импортирующим функцию TakesListStruct и содержит структуру с именем MListStruct эквивалентно собственного ListStruct за исключением того, что double * с <xref:System.IntPtr> экземпляра. Перед вызовом TakesListStruct основная функция выделяет и инициализирует память, на который ссылается это поле.  
  
 Управляемый модуль компилируется с параметром/CLR, но/CLR: pure работает также. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
```cpp  
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
  
```cpp  
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
  
 Обратите внимание, что никакие компоненты библиотеки DLL не предоставляются для управляемого кода, с помощью стандартной #include. На самом деле DLL осуществляется во время выполнения, поэтому проблемы с функциями импортированы с <xref:System.Runtime.InteropServices.DllImportAttribute> во время компиляции не обнаруживаются.  
  
## <a name="see-also"></a>См. также  
 [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)