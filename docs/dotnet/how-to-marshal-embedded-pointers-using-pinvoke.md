---
title: Практическое руководство. Маршалинг встроенных указателей посредством PInvoke
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
ms.openlocfilehash: 943a1a2784a37353157cd38da7ebdc9827006fe5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738759"
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>Практическое руководство. Маршалинг встроенных указателей посредством PInvoke

Функции, реализованные в неуправляемых библиотек DLL могут вызываться из управляемого кода с помощью функциональной возможности вызова неуправляемого кода (P/Invoke). Если исходный код для библиотеки DLL не доступен, P/Invoke является единственным для взаимодействия. Тем не менее в отличие от других языков .NET, Visual C++ предоставляет альтернативу P/Invoke. Дополнительные сведения см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) и [как: Маршалинг встроенных указателей посредством взаимодействия C++](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).

## <a name="example"></a>Пример

Передача структур в машинный код требует, что создается управляемую структуру, которая с точки зрения макет данных эквивалентна собственной структуры. Тем не менее структуры, содержащие указатели требуют специальной обработки. Для каждого внедренного указателя в собственной структуры, управляемой версии структуры должно содержать экземпляр <xref:System.IntPtr> типа. Кроме того, память для этих экземпляров должен быть выделен явным образом, инициализирован и освобожден посредством <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>, и <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> методы.

Следующий код состоит из неуправляемый и управляемый модуль. Неуправляемый модуль представляет собой DLL, определяет функцию, которая принимает ListString, которая содержит указатель на структуру и функции с именем TakesListStruct. Управляемый модуль является приложением командной строки, которое импортирует функцию TakesListStruct и определяет структуру, называемую MListStruct эквивалентно собственного ListStruct за исключением того, что двойной * с <xref:System.IntPtr> экземпляра. Перед вызовом TakesListStruct основная функция выделяет и инициализирует память, которая ссылается на это поле.

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

Обратите внимание, что часть библиотеки DLL предоставляется управляемого кода, с помощью стандартной #include. На самом деле, библиотеки DLL осуществляется во время выполнения, поэтому проблемы с функциями импортированы с <xref:System.Runtime.InteropServices.DllImportAttribute> не обнаруживаются во время компиляции.

## <a name="see-also"></a>См. также

[Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
