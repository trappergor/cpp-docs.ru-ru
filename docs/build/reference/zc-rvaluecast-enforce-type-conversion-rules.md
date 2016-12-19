---
title: "/Zc:rvalueCast (принудительное применение правил преобразования типов) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rvaluecast"
  - "/Zc:rvalueCast"
  - "VC.Project.VCCLCompilerTool.EnforceTypeConversionRules"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc - параметры компилятора (C++)"
  - "принудительное применение правил преобразования типов"
  - "rvaluecast"
  - "Zc - параметры компилятора (C++)"
  - "-Zc - параметры компилятора (C++)"
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:rvalueCast (принудительное применение правил преобразования типов)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если параметр **\/Zc:rvalueCast** указан, компилятор правильно определяет ссылочный тип rvalue как результат операции приведения в соответствие со стандартом C\+\+11.  Если этот параметр не задан, поведение компилятора является таким же, как в Visual Studio 2012.  По умолчанию параметр **\/Zc:rvalueCast** отключен.  Чтобы обеспечить соответствие и избежать ошибок при использовании приведений, рекомендуется использовать параметр **\/Zc:rvalueCast**.  
  
## Синтаксис  
  
```  
/Zc:rvalueCast[-]  
```  
  
## Заметки  
 Если указан параметр **\/Zc:rvalueCast**, компилятор следует разделу 5.4 стандарта C\+\+11 и рассматривает как типы rvalue только выражения приведения, дающие нессылочные типы, и выражения приведения, дающие ссылки rvalue на типы, не являющиеся функциями.  По умолчанию или если указан параметр **\/Zc:rvalueCast\-**, компилятор не обеспечивает соответствие стандарту и рассматривает все выражения приведения, которые приводят к созданию ссылок rvalue, как значения rvalue.  
  
 Используйте **\/Zc:rvalueCast** при передаче выражения приведения в качестве аргумента в функцию, которая принимает ссылочный тип rvalue.  Реакция на событие по умолчанию вызывает ошибку компилятора [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md), если компилятор неправильно определяет тип выражения приведения.  В этом примере показана ошибка компилятора в правильном коде, если параметр \/Zc:rvalueCast не задан.  
  
```cpp  
// Test of /Zc:rvalueCast  
// compile by using:  
// cl /c /Zc:rvalueCast- make_thing.cpp  
// cl /c /Zc:rvalueCast make_thing.cpp  
  
#include <utility>  
  
template <typename T>   
struct Thing {  
   // Construct a Thing by using two rvalue reference parameters  
   Thing(T&& t1, T&& t2)  
      : thing1(t1), thing2(t2) {}  
  
   T& thing1;  
   T& thing2;  
};  
  
// Create a Thing, using move semantics if possible  
template <typename T>  
Thing<T> make_thing(T&& t1, T&& t2)  
{  
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));  
}  
  
struct Test1 {  
   long a;  
   long b;  
  
   Thing<long> test() {   
      // Use identity casts to create rvalues as arguments  
      return make_thing(static_cast<long>(a), static_cast<long>(b));   
   }  
};  
  
```  
  
 По умолчанию компилятор может не сообщать об ошибке C2102, когда это необходимо.  В этом примере компилятор не сообщает об ошибке, если берется адрес значения rvalue, созданного путем приведения идентификатора, когда параметр **\/Zc:rvalueCast** не задан.  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Подробнее о вопросах соответствия в Visual C\+\+ см. в статье [Нестандартное поведение](../Topic/Nonstandard%20Behavior.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Измените свойство **Дополнительные параметры**, включив параметр **\/Zc:rvalueCast**, а затем нажмите кнопку **ОК**.  
  
## См. также  
 [\/Zc \(соответствие\)](../../build/reference/zc-conformance.md)