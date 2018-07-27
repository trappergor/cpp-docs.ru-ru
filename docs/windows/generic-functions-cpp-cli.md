---
title: Универсальные функции (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 66eb27b28a1b18942c0a8a9a77a877a2f0b2ef8c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878838"
---
# <a name="generic-functions-ccli"></a>Универсальные функции (C++/CLI)
Универсальная функция — это функция, объявляемая с параметрами типа. При ее вызове вместо параметров типа используются фактические типы.  
  
## <a name="all-platforms"></a>Все платформы  
 **Заметки**  
  
 Эта возможность применяется не для всех платформ.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 **Заметки**  
  
 Эта функция не поддерживается в среде выполнения Windows.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 Универсальная функция — это функция, объявляемая с параметрами типа. При ее вызове вместо параметров типа используются фактические типы.  
  
 **Синтаксис**  
  
```  
[attributes] [modifiers]  
return-type identifier<type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{function-body}  
```  
  
 **Параметры**  
  
 *атрибуты* (необязательно)  
 Дополнительные описательные данные. Дополнительные сведения об атрибутах и классах атрибутов см. в разделе "Атрибуты".  
  
 *модификаторы* (необязательно)  
 Модификатор для функции, такие как статический.  `virtual` запрещено, так как виртуальные методы не могут быть универсальными.  
  
 *Тип возвращаемого значения*  
 Тип, возвращаемый этим методом. Если тип возвращаемого значения — void, возвращаемое значение не требуется.  
  
 *identifier*  
 Имя функции.  
  
 *идентификаторы параметров типа*  
 Разделенный запятыми список идентификаторов.  
  
 *формальных параметров* (необязательно)  
 Список параметров.  
  
 *Тип параметра — ограничения предложения*  
 Это определяет ограничения на типы, которые могут использоваться как аргументы типа и принимает форму, указанный в [ограничений для параметров универсального типа (C + +/ CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
 *тело функции*  
 Тело метода, который может ссылаться на идентификаторы параметров типа.  
  
 **Заметки**  
  
 Универсальные функции — это функции, объявленные с параметром универсального типа. Они могут быть методами в классе или структуре или автономными функциями. В одном универсальном объявлении неявно объявляется семейство функций, отличающихся только подстановкой различных фактических типов вместо параметра универсального типа.  
  
 В Visual C++ конструкторы класса или структуры не могут объявляться с параметрами универсального типа.  
  
 При вызове параметр универсального типа заменяется фактическим типом. Фактический тип может быть явно указан в угловых скобках с использованием синтаксиса, аналогичного синтаксису вызова шаблонной функции. При вызове без параметров типа компилятор будет пытаться определить фактический тип по параметрам, указанным в вызове функции. Если определить заданный аргумент типа по используемым параметрам не удается, компилятор выдает ошибку.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
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
  
 Универсальные функции могут перегружаться на основе сигнатуры или арности (количества параметров типа для функции). Кроме того универсальные функции могут перегружаться неуниверсальными функциями с таким же именем при условии, что функции отличаются некоторыми параметрами типа. Например, могут перегружаться следующие функции:  
  
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
  
 В следующем примере используется универсальная функция, чтобы найти первый элемент массива. В примере объявляется класс `MyClass`, который наследуется от базового класса `MyBaseClass`. `MyClass` содержит универсальную функцию `MyFunction`, вызывающую другую универсальную функцию `MyBaseClassFunction` в базовом классе. В **основной**, универсальная функция `MyFunction`, вызывается с использованием разных аргументов типа.  
  
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
  
 **Вывод**  
  
```Output  
My function returned an int: 2003  
My function returned a string: Hello generic functions!  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md)