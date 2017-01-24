---
title: "Универсальные функции (C++/CLI) | Microsoft Docs"
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
  - "функции [C++], универсальный"
  - "универсальные функции"
  - "универсальные методы"
  - "универсальные [C++], функции"
  - "методы [C++], универсальный"
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Универсальные функции (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Универсальная функция \- это функция, объявленная с параметрами типа.  При вызове вместо параметров типа используются фактические типы.  
  
## Все платформы  
 **Примечания**  
  
 Эта функция не применяется ко всем платформам.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Примечания**  
  
 Данная функция не поддерживается в [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Универсальная функция \- это функция, объявленная с параметрами типа.  При вызове вместо параметров типа используются фактические типы.  
  
 **Синтаксис**  
  
```  
[attributes] [modifiers]  
return-type identifier <type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{  
   function-body  
}  
```  
  
 **Параметры**  
  
 *attributes* \(необязательный\)  
 Дополнительные описательные данные.  Дополнительные сведения об атрибутах и классах атрибутов см. в атрибутах.  
  
 *modifiers* \(необязательный\)  
 Модификаторы для функции, например `static` или `virtual` недопустимы, так как виртуальные методы могут не быть универсальными.  
  
 *return\-type*  
 Тип, возвращаемый методом.  Если типом возвращаемого значения является void, возвращаемого значения не требуется.  
  
 *identifier*  
 Имя функции.  
  
 *type\-parameter identifier\(s\)*  
 Разделенный запятыми список идентификаторов.  
  
 *formal\-parameters* \(необязательный\)  
 Список параметров.  
  
 *type\-parameter\-constraints\-clauses*  
 Указывает ограничения для типов, которые могут использоваться в качестве аргументов типа, и принимает форму, определенную в разделе [Ограничения, применяемые к параметрам универсальных типов \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md).  
  
 *function\-body*  
 Тело метода, который может обращаться к идентификаторам параметра типа.  
  
 **Примечания**  
  
 Универсальные функции \- функции, объявленные с параметром универсального типа.  Они могут быть методами в классе или структуре, или как отдельными функциями.  Одно универсальное объявление неявно объявляет семейство функций, которые отличаются только подстановкой различных фактических типов параметра вместо универсального типа.  
  
 В [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], конструкторы класса или структуры могут быть не объявлены с параметрами универсального типа.  
  
 При вызове, параметр универсального типа заменяется фактическим типом.  Фактический тип может быть явно указан в угловых скобках, используя синтаксис, аналогичный вызову шаблонной функции.  При вызове без параметров типа, компилятор попытается вывести фактический тип из параметров в вызове функции.  Если не удается логически вывести предполагаемый аргумент типа на основании используемых параметров, возникает ошибка компилятора.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере кода демонстрируется универсальная функция.  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **Пример**  
  
 Универсальные функции могут перегружаться на основе сигнатуры или арности \(количества параметров типа для функции\).  Кроме того, универсальные функции могут перегружаться с неуниверсальными функциями с таким же именем, если функции имеют отличия в некоторых параметрах типа.  Например, могут быть перегружены следующие функции:  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **Пример**  
  
 В следующем примере используется универсальная функция, чтобы найти первый элемент массива.  Объявляется `MyClass`, который наследуется от базового класса `MyBaseClass`.  `MyClass` содержит универсальную функцию `MyFunction`, которая вызывает другую универсальную функцию `MyBaseClassFunction` в базовом классе.  В **main** универсальная функция `MyFunction` вызывается с аргументами различного типа.  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **Output**  
  
  **My function returned an int: 2003**  
 **My function returned a string: Hello generic functions\!**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md)