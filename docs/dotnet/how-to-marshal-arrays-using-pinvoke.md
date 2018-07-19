---
title: 'Как: маршалинг массивов с помощью PInvoke | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03e3cf184828c33c63c5252344eb0041640729cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132535"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>Практическое руководство. Маршалинг массивов с помощью службы PInvoke
В этом разделе объясняется, как собственных функций, принимающих строки в стиле C может вызываться с помощью строкового типа среды CLR <xref:System.String> с помощью поддержки вызова платформы .NET Framework. Программистам Visual C++, рекомендуется использовать возможности взаимодействия C++ (когда это возможно), поскольку P/Invoke предоставляет мало времени компиляции сведений об ошибках, не является строго типизированным и может оказаться трудоемкой для реализации. Если неуправляемый интерфейс API упакован как библиотека DLL и исходный код недоступен, P/Invoke является единственным параметром (см. в противном случае [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)).  
  
## <a name="example"></a>Пример  
 Так как машинные и управляемые массивы располагаются по-разному в памяти, успешная передача их через границу управляемого и неуправляемого требует или маршалинга. В этом разделе показано, как массив простых (не преобразуемых) элементов может быть передан неуправляемых функций из управляемого кода.  
  
 Как и в общем случае маршалинга управляемых и неуправляемых данных <xref:System.Runtime.InteropServices.DllImportAttribute> атрибут используется для создания управляемую точку входа для каждой собственной функции, которая будет использоваться. В случае функций, которые принимают массивов в качестве аргументов <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут должен использоваться также для указания компилятору способ маршалинга данных. В следующем примере <xref:System.Runtime.InteropServices.UnmanagedType> перечисление используется для указания, что управляемый массив будет маршалироваться как массив в стиле.  
  
 Следующий код состоит из неуправляемый и управляемый модуль. Неуправляемый модуль является библиотекой DLL, определяющей функцию, которая принимает массив целых чисел. Второй модуль представляет собой управляемое приложение командной строки, который импортирует данную функцию, но определяет ее в терминах управляемого массива и использует <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут, чтобы указать, что массив должен быть конвертирован в машинный массив при вызове.  
  
 Управляемый модуль компилируется с параметром/CLR.  
  
```cpp  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```cpp  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 Обратите внимание, что никакие компоненты библиотеки DLL не предоставляются для управляемого кода посредством традиционные #include. На самом деле, так как библиотеки DLL осуществляется только во время выполнения, проблемы с функциями импортированы с <xref:System.Runtime.InteropServices.DllImportAttribute> во время компиляции не обнаруживаются.  
  
## <a name="see-also"></a>См. также  
 [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)