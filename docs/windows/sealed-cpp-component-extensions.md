---
title: "запечатанные (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sealed_cpp
- sealed
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb8a8b7ea695d878235898a8741adf04ba91748c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="sealed--c-component-extensions"></a>sealed (расширения компонентов C++)
`sealed` — это контекстно-зависимое ключевое слово для ссылочных классов, которое означает, что виртуальный член нельзя переопределить или что тип не может использоваться в качестве базового типа.  
  
> [!NOTE]
>  ISO C ++ 11 стандартный язык имеет [окончательного](../cpp/final-specifier.md) ключевое слово, которое поддерживается в Visual Studio. Используйте `final` в стандартных классов, а `sealed` в ссылочных классах.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
  
## <a name="syntax"></a>Синтаксис
  
```  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
```  
  
### <a name="parameters"></a>Параметры  
  
 *identifier*  
 Имя функции или класса.  
  
 *Тип возвращаемого значения*  
 Тип, который возвращается функцией.  
  
## <a name="remarks"></a>Примечания  
  
 В первом примере синтаксиса запечатан (sealed) класс. Во втором примере запечатана виртуальная функция.  
  
 `sealed` Ключевое слово может использоваться для компиляции в машинный код, а также для среды выполнения Windows и общеязыковой среды выполнения (CLR). Дополнительные сведения см. в разделе [спецификаторы переопределения и компиляция в машинный код](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Во время компиляции можно определить, является ли тип запечатанным с помощью `__is_sealed(type)` Признак типа. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 `sealed` — контекстно-зависимое ключевое слово.  Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 В разделе [классы и структуры ссылки](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR  
 (Отсутствуют комментарии для этой функции языка, которая применяется только в среде CLR).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 В следующем примере кода показано влияние `sealed` на виртуальный член.  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
```Output  
X::f override of I1::f  
X::f override of I1::g  
Y::f override of I1::f  
```  
  
 В следующем примере кода показано, как пометить класс запечатанным.  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)