---
title: "new (новый слот в vtable) (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "new - ключевое слово [C++]"
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new (новый слот в vtable) (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `new` указывает, что виртуальный член получит новую ячейку в таблице vtable.  
  
> [!NOTE]
>  Ключевое слово `new` имеет много применений и значений.  Дополнительные сведения см. в разделе устранения неточностей [new](../misc/new.md).  
  
## Все среды выполнения  
 \(Отсутствует комментарий для этой функции языка, которая применяется ко всем средам выполнения\).  
  
## среда выполнения Windows  
 Не поддерживается в [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
 В компиляции **\/clr** `new` означает, что виртуальный член получит новый слот в vtable; это значит, что функция не переопределяет метод базового класса.  
  
 `new` вызывает модификатор newslot для добавления в IL для функции.  Дополнительные сведения о newslot см. в  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="e9bb59a12f97840a5c3173bb77c6b5b1" class\="tgtSentence"\>Метод MethodInfo.GetBaseDefinition\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [\<caps:sentence id\="tgt12" sentenceid\="f6ceddd85a425f38e7ed06e94a9808a9" class\="tgtSentence"\>Перечисление MethodAttributes\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере показано действие `new`.  
  
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
  
 **Output**  
  
  **Вызывается C::f\(\)**  
 **Вызывается D::f\(\)**  
 **Вызывается D::g\(\)**  
 **Вызывается D::g\(\)**  
 **Вызывается E::f\(\)**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)