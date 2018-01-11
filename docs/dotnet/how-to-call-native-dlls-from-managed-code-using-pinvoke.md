---
title: "Как: вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d22f493a582b6ef09615f94c7b321a7cc535e5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke
Функции, реализованные в неуправляемых библиотек DLL может вызываться из управляемого кода с помощью функциональной возможности вызова неуправляемого кода (P/Invoke). Если исходный код для библиотеки DLL недоступен, P/Invoke является единственным вариантом обеспечения взаимодействия. Однако в отличие от других языков .NET, Visual C++ предоставляет альтернативы P/Invoke. Дополнительные сведения см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется Win32 [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) функции для получения текущего разрешения экрана в пикселях.  
  
 Для функций, используйте только внутренние типы в качестве аргументов и возвращаемых значений дополнительные действия не требуется. Другие типы данных, такие как указатели функций, массивы и структуры, требуются дополнительные атрибуты, чтобы обеспечить правильный маршалинг данных.  
  
 Несмотря на то, что это не обязательно, рекомендуется сделать объявления P/Invoke статические члены класса значений, чтобы они не существуют в глобальном пространстве имен, как показано в следующем примере.  
  
```  
// pinvoke_basic.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value class Win32 {  
public:  
   [DllImport("User32.dll")]  
   static int GetSystemMetrics(int);  
  
   enum class SystemMetricIndex {  
      // Same values as those defined in winuser.h.  
      SM_CXSCREEN = 0,  
      SM_CYSCREEN = 1  
   };  
};  
  
int main() {  
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );  
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );  
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)