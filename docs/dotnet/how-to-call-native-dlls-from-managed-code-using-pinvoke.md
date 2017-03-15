---
title: "Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "маршалинг данных [C++], вызов собственных библиотек DLL"
  - "взаимодействие [C++], вызов собственных библиотек DLL"
  - "маршалинг [C++], вызов собственных библиотек DLL"
  - "вызов неуправляемого кода [C++], вызов собственных библиотек DLL"
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функции, реализованные в неуправляемых библиотеках DLL, могут вызываться из управляемого кода с помощью вызова неуправляемого кода P\/Invoke.  Если исходный код библиотеки DLL недоступен, вызов P\/Invoke является единственным вариантом обеспечения взаимодействия.  В отличие от других языков .NET в Visual C\+\+ предусматривается альтернатива вызову P\/Invoke.  Для получения дополнительной информации см. [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## Пример  
 В следующем примере функция Win32 [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) используется для получения текущего значения разрешения экрана в пикселях.  
  
 Для функций, в которых используются аргументы и возвращаемые значения встроенных типов, дополнительные действия не требуются.  Для других типов данных, например указателей на функции, массивов и структур, требуется наличие дополнительного атрибута, гарантирующего правильный маршалинг данных.  
  
 Рекомендуется \(но не обязательно\) объявлять вызовы P\/Invoke как статические члены класса значений, что позволяет не включать их в глобальное пространство имен, как показано в следующем примере.  
  
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
  
## См. также  
 [Использование явного вызова Pinvoke в C\+\+ \(атрибут DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)