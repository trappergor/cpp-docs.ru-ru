---
title: "Практическое руководство. Хранение ссылки на объект в неуправляемой памяти | Microsoft Docs"
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
  - "gcroot - зарезервированное слово [C++], ссылка на объект в собственной функции"
  - "ссылки для объектов, в собственной функции"
  - "объекты [C++], ссылка собственной функции"
  - "ссылки, на объект в собственных функциях"
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Хранение ссылки на объект в неуправляемой памяти
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для хранения ссылки на объект CLR в неуправляемой памяти можно использовать заголовочный файл gcroot.h, который содержит объект <xref:System.Runtime.InteropServices.GCHandle>.  В качестве альтернативного варианта можно напрямую использовать структуру `GCHandle`.  
  
## Пример  
  
```  
// hold_object_reference.cpp  
// compile with: /clr  
#include "gcroot.h"  
using namespace System;  
  
#pragma managed  
class StringWrapper {  
  
private:  
   gcroot<String ^ > x;  
  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      x = str;  
   }  
  
   void PrintString() {  
      String ^ targetStr = x;  
      Console::WriteLine("StringWrapper::x == {0}", targetStr);  
   }  
};  
#pragma unmanaged  
int main() {  
   StringWrapper s;  
   s.PrintString();  
}  
```  
  
  **StringWrapper::x \=\= ManagedString**   
## Пример  
 Структура `GCHandle` предоставляет возможность хранения ссылки на управляемый объект в неуправляемой памяти.  Для создания непрозрачного дескриптора для управляемого объекта можно использовать метод <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> и метод <xref:System.Runtime.InteropServices.GCHandle.Free%2A> для его освобождения.  Помимо этого метод <xref:System.Runtime.InteropServices.GCHandle.Target%2A> позволяет возвращать обратно ссылку на объект от дескриптора в управляемом коде.  
  
```  
// hold_object_reference_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
class StringWrapper {  
   IntPtr m_handle;  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));  
   }  
   ~StringWrapper() {  
      static_cast<GCHandle>(m_handle).Free();  
   }  
  
   void PrintString() {  
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);  
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);  
   }  
};  
  
#pragma unmanaged  
int main() {  
   StringWrapper s;   
   s.PrintString();  
}  
```  
  
  **StringWrapper::m\_handle \=\= ManagedString**   
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)