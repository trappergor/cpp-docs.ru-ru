---
title: "Упаковка-преобразование (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: boxing, Visual C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 15fa5471280935c54cdb936af378634e2b60cacd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="boxing--c-component-extensions"></a>Упаковка-преобразование (расширения компонентов C++)
Компилятор Visual C++ может преобразовывать типы значений в объекты в процессе, называемом *упаковка-преобразование*и преобразовывать объекты в типы значений в процессе, называемом *распаковки*.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 (Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 C + +/ CX поддерживает сокращенный синтаксис для упаковки-преобразования типов значений и распаковки-преобразования ссылочных типов. Тип значения упаковывается-преобразовывается, когда он присваивается переменной типа `Object`. Переменная `Object` распаковывается-преобразовывается, когда она присваивается переменной типа значения, и распакованный-преобразованный тип указывается в скобках; то есть когда объектная переменная приводится к типу значения.  
  
```  
  
  Platform::Object^  
  object_variable  = value_variable;  
value_variable = (value_type) object_variable;  
  
```  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
### <a name="examples"></a>Примеры  
 В следующем примере кода выполняется упаковка-преобразование и распаковка-преобразование значения `DateTime`. Сначала пример получает значение DateTime, представляющее текущую дату и время, и назначает его переменной DateTime. Затем эта переменная DateTime упаковывается-преобразовывается путем назначения ее переменной Object. Наконец, упакованное-преобразованное значение распаковывается-преобразуется путем его назначения другой переменной DateTime.  
  
 Чтобы протестировать пример, создайте проект BlankApplication, замените метод BlankPage::OnNavigatedTo(), а затем задайте точки останова в закрывающей скобке и назначение переменной str1. Когда пример достигает закрывающей скобки, проверьте str1.  
  
```  
  
void BlankPage::OnNavigatedTo(NavigationEventArgs^ e)  
{  
    using namespace Windows::Globalization::DateTimeFormatting;  
  
    Windows::Foundation::DateTime dt, dtAnother;  
    Platform::Object^ obj1;  
  
    Windows::Globalization::Calendar^ c =   
        ref new Windows::Globalization::Calendar;  
    c->SetToNow();  
    dt = c->GetDateTime();  
    auto dtf = ref new DateTimeFormatter(  
                           YearFormat::Full,   
                           MonthFormat::Numeric,   
                           DayFormat::Default,   
                           DayOfWeekFormat::None);  
    String^ str1 = dtf->Format(dt);  
    OutputDebugString(str1->Data());  
    OutputDebugString(L"\r\n");  
  
    // Box the value type and assign to a reference type.  
    obj1 = dt;  
    // Unbox the reference type and assign to a value type.  
    dtAnother = (Windows::Foundation::DateTime) obj1;  
  
    // Format the DateTime for display.  
    String^ str2 = dtf->Format(dtAnother);  
    OutputDebugString(str2->Data());  
}  
  
```  
  
 Дополнительные сведения см. в разделе [упаковка-преобразование (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh969554.aspx).  
  
## <a name="common-language-runtime"></a>Среда CLR  
 Компилятор Visual C++ теперь упаковывает-преобразовывает типы значений в <xref:System.Object>.  Это возможно благодаря преобразованию, заданному компилятором, для преобразования типов значений в <xref:System.Object>.  
  
 Упаковка-преобразование и распаковка-преобразование позволяют обрабатывать типы значений как объекты. Типы значений, включая типы структур и встроенные типы, такие как int, могут преобразовываться в тип <xref:System.Object> и из этого типа.  
  
 Дополнительные сведения:  
  
-   [Практическое руководство. Явный запрос упаковки-преобразования](../dotnet/how-to-explicitly-request-boxing.md)  
  
-   [Практическое руководство. Использование gcnew для создания типов значений и использование неявной упаковки-преобразования](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)  
  
-   [Практическое руководство. Распаковка-преобразование](../dotnet/how-to-unbox.md)  
  
-   [Стандартные преобразования и неявная упаковка-преобразование](../dotnet/standard-conversions-and-implicit-boxing.md)  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере демонстрируется, как работает неявная упаковка-преобразование.  
  
```cpp  
// vcmcppv2_explicit_boxing2.cpp  
// compile with: /clr  
using namespace System;  
  
ref class A {  
public:  
   void func(System::Object^ o){Console::WriteLine("in A");}  
};  
  
value class V {};  
  
interface struct IFace {  
   void func();  
};  
  
value class V1 : public IFace {  
public:  
   virtual void func() {  
      Console::WriteLine("Interface function");  
   }  
};  
  
value struct V2 {  
   // conversion operator to System::Object  
   static operator System::Object^(V2 v2) {  
      Console::WriteLine("operator System::Object^");  
      return (V2^)v2;  
   }  
};  
  
void func1(System::Object^){Console::WriteLine("in void func1(System::Object^)");}  
void func1(V2^){Console::WriteLine("in func1(V2^)");}  
  
void func2(System::ValueType^){Console::WriteLine("in func2(System::ValueType^)");}  
void func2(System::Object^){Console::WriteLine("in func2(System::Object^)");}  
  
int main() {  
   // example 1 simple implicit boxing  
   Int32^ bi = 1;  
   Console::WriteLine(bi);  
  
   // example 2 calling a member with implicit boxing  
   Int32 n = 10;  
   Console::WriteLine("xx = {0}", n.ToString());  
  
   // example 3 implicit boxing for function calls  
   A^ a = gcnew A;  
   a->func(n);  
  
   // example 4 implicit boxing for WriteLine function call  
   V v;  
   Console::WriteLine("Class {0} passed using implicit boxing", v);  
   Console::WriteLine("Class {0} passed with forced boxing", (V^)(v));   // force boxing  
  
   // example 5 casting to a base with implicit boxing  
   V1 v1;  
   IFace ^ iface = v1;  
   iface->func();  
  
   // example 6 user-defined conversion preferred over implicit boxing for function-call parameter matching  
   V2 v2;  
   func1(v2);   // user defined conversion from V2 to System::Object preferred over implicit boxing  
                // Will call void func1(System::Object^);  
  
   func2(v2);   // OK: Calls "static V2::operator System::Object^(V2 v2)"  
   func2((V2^)v2);   // Using explicit boxing: calls func2(System::ValueType^)  
}  
```  
  
 **Вывод**  
  
```Output  
1  
  
xx = 10  
  
in A  
  
Class V passed using implicit boxing  
  
Class V passed with forced boxing  
  
Interface function  
  
in func1(V2^)  
  
in func2(System::ValueType^)  
  
in func2(System::ValueType^)  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)