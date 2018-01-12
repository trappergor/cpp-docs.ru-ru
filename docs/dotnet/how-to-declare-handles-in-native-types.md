---
title: "Как: объявление дескрипторов в собственных типах | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords: gcroot
dev_langs: C++
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 097889acd9a77cea5e0a81dd3bd13be712a70550
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-declare-handles-in-native-types"></a>Практическое руководство. Объявление дескрипторов в собственных типах
Нельзя объявить тип дескриптора в собственном типе. в файле vcclr.h представлен шаблон строго типизированные оболочки `gcroot` для ссылки на объект CLR из кучи C++. Этот шаблон позволяет встраивать виртуальный дескриптор собственного типа и обработать его, как если бы это был базовый тип. В большинстве случаев можно использовать `gcroot` объект в качестве встроенного типа без приведения типов. Однако в [для каждой из них, в](../dotnet/for-each-in.md), вы должны использовать `static_cast` для извлечения базовой управляемой ссылки.  
  
 `gcroot` Шаблона реализуется с помощью средств значение класса System::Runtime::InteropServices::GCHandle, который предоставляет «маркеры» в куче сбора мусора. Обратите внимание, что сами дескрипторы не собираются и удаляются, при они больше не используются, деструктором `gcroot` класса (вручную вызвать его нельзя). При создании экземпляра `gcroot` объекта в собственной куче необходимо вызвать удаление в этом ресурсе.  
  
 Среда выполнения поддерживает связь между дескриптором и объектом CLR, на который он ссылается. Когда объект CLR перемещается вместе с куче сбора мусора, дескриптор возвращает новый адрес объекта. Переменная не должен быть закреплен, прежде чем он назначен `gcroot` шаблона.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как создать `gcroot` объекта на собственный стек.  
  
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
  
```Output  
hello  
```  
  
## <a name="example"></a>Пример  
 В этом примере показано, как создать `gcroot` объект в собственной куче.  
  
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
  
```Output  
hello  
```  
  
## <a name="example"></a>Пример  
 В этом примере показано, как использовать `gcroot` для хранения ссылок на типы значения (не ссылочные типы) в собственном типе с помощью `gcroot` на упакованный тип.  
  
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
  
```Output  
String in V: Hello  
```  
  
## <a name="see-also"></a>См. также  
 [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)