---
title: "Literal (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- literal
- literal_cpp
dev_langs: C++
helpviewer_keywords: literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f858e94bf916c2d441cee607739bb9e08da09b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="literal-c-component-extensions"></a>literal (расширения компонентов C++)
Переменная (элемент данных) помечен как `literal` в **/CLR** компиляции эквивалентно собственного `static const` переменной.  
  
## <a name="all-platforms"></a>Все платформы  
 **Заметки**  
  
 (Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 **Заметки**  
  
 (Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR  
  
## <a name="remarks"></a>Примечания  
 Член данных помечен как `literal` должны быть инициализированы при объявлении и значение должны иметь целочисленные константы, перечисления или строковый тип. Преобразование из типа выражения инициализации в тип статического константного элемента данных не должно требовать определенного пользователем преобразования.  
  
 Во время выполнения для полей литералов память не выделяется; компилятор только вставляет свое значение в метаданные класса.  
  
 Переменная, помеченная как `static const`, не будет доступна в метаданных другим компиляторам.  
  
 Дополнительные сведения см. в разделе [статических](../cpp/storage-classes-cpp.md) и [const](../cpp/const-cpp.md).  
  
 `literal` — контекстно-зависимое ключевое слово. В разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, что переменная `literal` подразумевает ключевое слово `static`.  
  
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
  
## <a name="example"></a>Пример  
 В следующем примере показано влияние литералов в метаданных.  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 Обратите внимание на разницу в метаданных для `sc` и `lit`: директива `modopt` применяется к `sc` и поэтому она может игнорироваться другими компиляторами.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## <a name="example"></a>Пример  
 В следующем примере, написанном на языке C#, осуществляется ссылка на метаданные, созданные в предыдущем примере, и показывается влияние переменных `literal` и `static const`.  
  
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
  
## <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)