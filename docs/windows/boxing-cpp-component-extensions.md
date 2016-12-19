---
title: "Упаковка-преобразование (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "упаковка-преобразование, Visual C++"
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Упаковка-преобразование (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Компилятор Visual C\+\+ может преобразовывать типы значений в объекты в процессе, называемом *упаковкой\-преобразованием*, и преобразовывать объекты в типы значений в процессе, называемом *распаковкой\-преобразованием*.  
  
## Все среды выполнения  
 \(Отсутствуют комментарии для этой функции языка, которая применяется во всех средах выполнения.\)  
  
## Среда выполнения Windows  
 [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] поддерживает сокращенный синтаксис для упаковки\-преобразования типов значений и распаковки\-преобразования ссылочных типов.  Тип значения упаковывается\-преобразовывается, когда он присваивается переменной типа `Object`.  Переменная `Object` распаковывается\-преобразовывается, когда она присваивается переменной типа значения, и распакованный\-преобразованный тип указывается в скобках; то есть когда объектная переменная приводится к типу значения.  
  
```  
  
Platform::Object^ object_variable  = value_variable;  
value_variable = (value_type) object_variable;  
  
```  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
### Примеры  
 В следующем примере кода выполняется упаковка\-преобразование и распаковка\-преобразование значения `DateTime`.  Сначала пример получает значение DateTime, представляющее текущую дату и время, и назначает его переменной DateTime.  Затем эта переменная DateTime упаковывается\-преобразовывается путем назначения ее переменной Object.  Наконец, упакованное\-преобразованное значение распаковывается\-преобразуется путем его назначения другой переменной DateTime.  
  
 Чтобы протестировать пример, создайте проект BlankApplication, замените метод BlankPage::OnNavigatedTo\(\), а затем задайте точки останова в закрывающей скобке и назначение переменной str1.  Когда пример достигает закрывающей скобки, проверьте str1.  
  
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
  
 Дополнительные сведения см. в разделе [Упаковка\-преобразование \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh969554.aspx).  
  
## Среда CLR  
 Компилятор Visual C\+\+ теперь упаковывает\-преобразовывает типы значений в <xref:System.Object>.  Это возможно благодаря преобразованию, заданному компилятором, для преобразования типов значений в <xref:System.Object>.  
  
 Упаковка\-преобразование и распаковка\-преобразование позволяют обрабатывать типы значений как объекты.  Типы значений, включая типы структур и встроенные типы, такие как int, могут преобразовываться в тип <xref:System.Object> и из этого типа.  
  
 Дополнительные сведения:  
  
-   [Практическое руководство. Явный запрос упаковки\-преобразования](../Topic/How%20to:%20Explicitly%20Request%20Boxing.md)  
  
-   [Практическое руководство. Использование gcnew для создания типов значений, а также использование неявной упаковки\-преобразования](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)  
  
-   [Практическое руководство. Распаковка](../dotnet/how-to-unbox.md)  
  
-   [Стандартные преобразования и неявная упаковка\-преобразование](../dotnet/standard-conversions-and-implicit-boxing.md)  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере демонстрируется, как работает неявная упаковка\-преобразование.  
  
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
  
  **1**  
 **xx \= 10**  
 **in A**  
 **Class V passed using implicit boxing**  
 **Class V passed with forced boxing**  
 **Interface function**  
 **in func1\(V2^\)**  
 **in func2\(System::ValueType^\)**  
 **in func2\(System::ValueType^\)**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)