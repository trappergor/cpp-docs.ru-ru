---
title: "New (новый слот в vtable) (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f208a62fd49e7aea67acf5b7e3e49d3571f8d910
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>new (новый слот в vtable) (расширения компонентов C++)
`new` Ключевое слово указывает, что виртуальный член получает новую ячейку в таблице vtable.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 (Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Не поддерживается в среде выполнения Windows.  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 В **/CLR** компиляции `new` указывает, что виртуальный член получает новую ячейку в таблице vtable, что функция не переопределяет метод базового класса.  
  
 `new`в результате модификатор newslot добавляемый IL-код для функции.  Дополнительные сведения о newslot см. в разделе:  
  
-   [Метод MethodInfo.GetBaseDefinition](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [Перечисление MethodAttributes](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере показано влияние `new`.  
  
```  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **Вывод**  
  
```Output  
C::f() called  
  
D::f() called  
  
D::g() called  
  
D::g() called  
  
E::f() called  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)