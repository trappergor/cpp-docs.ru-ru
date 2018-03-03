---
title: "Явные переопределения (расширения компонентов C++) | Документы Microsoft"
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
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 346dd73952934d514b2741c41d5a27816b7152ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-overrides--c-component-extensions"></a>Явные переопределения (Расширения компонентов C++)
В этом разделе описывается, как явно переопределить член базового класса или интерфейса. Именованное переопределение (явно) должен использоваться только для переопределения одного метода производного метода, имеющего другое имя.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 **Синтаксис**  
  
```  
  
      overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Параметры**  
  
 *Переопределение функция декларатор*  
 Возвращаемый тип, имя и аргумент список переопределяющая функция.  Обратите внимание, что переопределяющая функция не имеет имя, совпадающее с именем переопределяемой функции.  
  
 *type*  
 Базовый тип, содержащий функцию для переопределения.  
  
 *function*  
 Список с разделителями запятыми одно или несколько имен функцию для переопределения.  
  
 *Переопределение определение функции*  
 Инструкции тела функции, определяющие переопределяющая функция.  
  
 **Заметки**  
  
 Используйте явные переопределения для создания псевдонима для сигнатуры метода, или можно определить разные реализации для методов witht такой же сигнатурой.  
  
 Сведения об изменении поведение унаследованных типов и наследуемые члены типа см. в разделе [спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 Сведения о явных переопределений в машинный код или код компилируется с **/CLR: oldSyntax**, в разделе [явное переопределение](../cpp/explicit-overrides-cpp.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода показан простой, неявное override и реализация члена в базовый интерфейс, не с помощью явного переопределения.  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **Вывод**  
  
```Output  
X::f override of I1::f  
```  
  
 **Пример**  
  
 В следующем примере кода показано, как реализовать все члены интерфейса с общей сигнатурой, используя синтаксис явного переопределения.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **Вывод**  
  
```Output  
X::f override of I1::f and I2::f  
X::f override of I1::f and I2::f  
```  
  
 **Пример**  
  
 В следующем примере кода показано, как переопределения функции может иметь имя, отличное от функции, которое он реализует.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **Вывод**  
  
```Output  
X::g  
```  
  
 **Пример**  
  
 В следующем примере кода показана реализация явный интерфейс, реализующий безопасном коллекцией типа.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)