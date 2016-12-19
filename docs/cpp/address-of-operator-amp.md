---
title: "Оператор address-of: &amp; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "address-of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& - оператор"
  - "& - оператор, address-of - оператор"
  - "address-of - оператор (&)"
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор address-of: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
& cast-expression  
```  
  
## Заметки  
 Унарный оператор взятия адреса \(**&**\) принимает адрес своего операнда.  Операнд операции взятия адреса может быть либо указателем функции, либо l\-значением, указывающим на объект, который не является битовым полем и не объявлен со спецификатором класса хранения **register**.  
  
 Оператор взятия адреса может применяться только к переменным фундаментального типа или типа структуры, класса или объединения, которые были объявлены в области видимости файла, а также к ссылкам на массив с индексом.  В таких выражениях из выражения взятия адреса можно вычитать \(или прибавлять к нему\) константное выражение, которое не содержит выражения взятия адреса.  
  
 Если этот оператор применяется к функциям или l\-значениям, то результатом является тип указателя \(r\-значение\), производный от типа операнда.  Например, если операнд имеет тип `char`, то результат выражения будет иметь тип указателя на `char`.  Оператор взятия адреса, примененный к объектам с ключевым словом **const** или `volatile`, имеет значение **const** `type` **\*** или `volatile` `type` **\***, где `type` означает тип исходного объекта.  
  
 Если оператор взятия адреса применяется к [полному\-имени](http://msdn.microsoft.com/ru-ru/3fefb16d-8120-4627-8b3f-3d90fbdcd1df), то результат зависит от того, определяет ли *полное\-имя* статический член.  Если да, то результатом является указатель на тип, заданный в определении этого члена.  Если же член не является статическим, то результатом является указатель на *имя* члена класса, обозначенного параметром *полное\-имя\-класса*. \(Дополнительные сведения о *полных\-именах\-классов* см. в разделе [Основные сведения](../cpp/primary-expressions.md).\) В следующем фрагменте кода показано, как отличается результат в зависимости от того, является ли элемент статическим.  
  
```  
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
           int   iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 В этом примере выражение `&PTM::fValue` имеет результатом тип `float *`, а не `float PTM::*`, поскольку `fValue` является статическим членом.  
  
 Адрес перегруженной функции можно принимать только в том случае, если очевидно, к какой именно версии этой функции привязана ссылка.  Сведения о том, как получить адрес конкретной перегруженной функции, см. в разделе [Адрес перегруженных функций](../misc/address-of-overloaded-functions.md).  
  
 Применение оператора взятия адреса к типу ссылки дает тот же результат, что и применение к объекту, к которому привязана ссылка.  Например:  
  
## Пример  
  
```  
// expre_Address_Of_Operator2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   double d;        // Define an object of type double.  
   double& rd = d;  // Define a reference to the object.  
  
   // Obtain and compare their addresses  
   if( &d == &rd )  
      cout << "&d equals &rd" << endl;  
}  
```  
  
## Вывод  
  
```  
&d equals &rd  
```  
  
 В следующем примере оператор взятия адреса используется для того, чтобы передать указатель в качестве аргумента функции:  
  
```  
// expre_Address_Of_Operator3.cpp  
// compile with: /EHsc  
// Demonstrate address-of operator &  
  
#include <iostream>  
using namespace std;  
  
// Function argument is pointer to type int  
int square( int *n ) {  
   return (*n) * (*n);  
}  
  
int main() {  
   int mynum = 5;  
   cout << square( &mynum ) << endl;   // pass address of int  
}  
```  
  
## Вывод  
  
```  
25  
```  
  
## См. также  
 [Выражения с унарными операторами](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Декларатор ссылки Lvalue: &](../Topic/Lvalue%20Reference%20Declarator:%20&.md)   
 [Операторы косвенного обращения и адреса операнда](../c-language/indirection-and-address-of-operators.md)