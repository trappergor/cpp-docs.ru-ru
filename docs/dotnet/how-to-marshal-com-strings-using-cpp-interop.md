---
title: 'Как: маршалирование строк COM с помощью взаимодействия C++ | Документы Microsoft'
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
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 918825dd6563f59167baa844b94edfc1033498a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Практическое руководство. Маршалирование строк COM с помощью взаимодействия C++
В этом разделе показано, как BSTR (основной формат строк в программировании COM) может быть передано из управляемой в неуправляемую функцию и наоборот. Дополнительные сведения о взаимодействии с другими типами строк, в следующих разделах:  
  
-   [Практическое руководство. Маршалинг строк Юникода с использованием взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Практическое руководство. Маршалинг строк ANSI с использованием взаимодействия C++](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 В следующем примере кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma управляемых и неуправляемых функций в одном файле, но эти функции взаимодействия так же, если они определены в отдельных файлах. Файлы, содержащие только неуправляемые функции, не обязательно должны быть скомпилированы с [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как можно передать BSTR (формат строки используются в программировании COM) из управляемой в неуправляемую функцию. В вызывающей управляемой функции используется <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> для получения адреса представления BSTR содержимое .NET System.String. Этот указатель закрепляется с помощью [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) чтобы убедиться, что его физический адрес не меняется во время цикла сбора мусора во время выполнения неуправляемой функции. Сборщик мусора не освобождает с перемещением памяти до [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) выходит за пределы области.  
  
```  
// MarshalBSTR1.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(BSTR bstr) {  
   printf_s("%S", bstr);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = "test string";  
  
   IntPtr ip = Marshal::StringToBSTR(s);  
   BSTR bs = static_cast<BSTR>(ip.ToPointer());  
   pin_ptr<BSTR> b = &bs;  
  
   NativeTakesAString( bs );  
   Marshal::FreeBSTR(ip);  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как можно передать BSTR из неуправляемой в неуправляемую функцию. Получение управляемой функции можно использовать строку в качестве BSTR или <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> для преобразования его в <xref:System.String> для использования в других управляемых функций. Поскольку память, представляющая строку BSTR выделяется в неуправляемой куче нет закрепление не требуется, так как отсутствует коллекция сборки мусора в неуправляемой куче.  
  
```  
// MarshalBSTR2.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedTakesAString(BSTR bstr) {  
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));  
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);  
}  
  
#pragma unmanaged  
  
void UnManagedFunc() {  
   BSTR bs = SysAllocString(L"test string");  
   printf_s("(unmanaged) passing BSTR to managed func...\n");  
   ManagedTakesAString(bs);  
}  
  
#pragma managed  
  
int main() {  
   UnManagedFunc();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)