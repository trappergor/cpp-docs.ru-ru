---
title: "Практическое руководство. Объявление дескрипторов в собственных типах | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcroot - зарезервированное слово [C++]"
  - "дескрипторы, объявление"
  - "типы [C++], обработчики объявлений"
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Практическое руководство. Объявление дескрипторов в собственных типах
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип дескриптора невозможно объявить в собственном типе. vcclr.h предоставляет типобезопасный шаблон `gcroot` оболочки для ссылки на объект CLR из кучи C C\+\+.  Этот шаблон позволяет встраивать виртуальный дескриптор в собственный тип и обрабатывать его, как любой базовый тип.  В большинстве случаев объект `gcroot` можно использовать в качестве встроенного типа без приведения типов.  Однако при наличии [for each, in](../dotnet/for-each-in.md) необходимо использовать `static_cast` для извлечения базовой управляемой ссылки.  
  
 Шаблон `gcroot` реализован с помощью средств класса System::Runtime::InteropServices::GCHandle, который предоставляет "дескрипторы" в куче со сбором мусора.  Обратите внимание, что сами дескрипторы не собираются и удаляются, когда они больше не используются, деструктором класса `gcroot` \(вручную вызвать его нельзя\).  При создании экземпляра объекта `gcroot` в собственной куче необходимо вызвать удаление в этом ресурсе.  
  
 Среда выполнения поддерживает связь между дескриптором и объектом CLR, на который он ссылается.  Когда объект CLR перемещается вместе с кучей со сбором мусора, дескриптор возвращает новый адрес объекта.  Перед назначением переменной шаблону `gcroot` закреплять ее не требуется.  
  
## Пример  
 В этом примере показано, как создать объект `gcroot` в собственном стеке.  
  
```  
// mcpp_gcroot.cpp  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
class CppClass {  
public:  
   gcroot<String^> str;   // can use str as if it were String^  
   CppClass() {}  
};  
  
int main() {  
   CppClass c;  
   c.str = gcnew String("hello");  
   Console::WriteLine( c.str );   // no cast required  
}  
```  
  
  **hello**   
## Пример  
 В этом примере показано, как создать объект `gcroot` в собственной куче.  
  
```  
// mcpp_gcroot_2.cpp  
// compile with: /clr  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
struct CppClass {  
   gcroot<String ^> * str;  
   CppClass() : str(new gcroot<String ^>) {}  
  
   ~CppClass() { delete str; }  
  
};  
  
int main() {  
   CppClass c;  
   *c.str = gcnew String("hello");  
   Console::WriteLine( *c.str );  
}  
```  
  
  **hello**   
## Пример  
 В этом примере показано, как применить `gcroot` для сохранения ссылок на типы значения \(не ссылочные типы\) в собственном типе, используя объект `gcroot` в упакованном типе.  
  
```  
// mcpp_gcroot_3.cpp  
// compile with: /clr  
#include < vcclr.h >  
using namespace System;  
  
public value struct V {  
   String^ str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
  **Строка в V: Hello**   
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)