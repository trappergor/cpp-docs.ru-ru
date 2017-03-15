---
title: "literal (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "literal"
  - "literal_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "literal - ключевое слово [C++]"
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# literal (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Переменная \(элемент данных\), помеченная как `literal` в компиляции **\/clr** является эквивалентом `static const` переменной.  
  
## Все платформы  
 **Примечания**  
  
 \(Отсутствует комментарий для этой функции языка, которая применяется ко всем средам выполнения\).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Примечания**  
  
 \(Отсутствуют комментарии для этой функции языка, которая применяется только в среде выполнения Windows\).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## Среда CLR  
  
## Заметки  
 Элемент данных, помеченный как `literal`, необходимо инициализировать при объявлении, и значение должно быть целой константой, перечислением или строковым типом.  Преобразование из типа выражения инициализации к типу статического константного члена данных не должно требовать определенного пользователем преобразования.  
  
 Во время выполнения для полей литералов память не выделяется; компилятор только вставляет его значение в метаданные класса.  
  
 Переменная, помеченная как `static const`, не будет доступна в метаданных другим компиляторам.  
  
 Дополнительные сведения см. в разделах [Static](../misc/static-cpp.md) и [const](../cpp/const-cpp.md).  
  
 `literal` — это контекстно\-зависимое ключевое слово.  Дополнительные сведения см. в разделе [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Пример  
 В этом примере показано, что переменная `literal` подразумевает модификатор `static`.  
  
```  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## Пример  
 В следующем примере показано влияние литералов в метаданных:  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 Обратите внимание на разницу в метаданных для `sc` и `lit`: директива `modopt` применяется к `sc`, а значит она может быть пропущена другими компиляторами.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## Пример  
 Следующий пример, написанный на C\#, ссылается на метаданные, созданные в предыдущем примере и отображает влияние `literal` и `static const` переменных:  
  
```  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## Требования  
 Параметр компилятора: **\/clr**  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)