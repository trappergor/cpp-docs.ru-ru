---
title: "Оператор address-of: &amp; | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 56e2606759cc381c1ae6f6f4f1f7cbc1d9d2d810
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="address-of-operator-amp"></a>Оператор address-of:&amp;
## <a name="syntax"></a>Синтаксис  
  
```  
& cast-expression  
```  
  
## <a name="remarks"></a>Примечания  
 Унарный оператор взятия адреса (**&**) принимает адрес своего операнда. Для оператора взятия адреса операнд может быть указателем функции либо левосторонним значением, указывающим на объект, который не является битовым полем и не объявлен с описателем класса хранения **register**.  
  
 Оператор взятия адреса может применяться только к переменным фундаментального типа или типа структуры, класса или объединения, которые были объявлены в области видимости файла, а также к ссылкам на массив с индексом. В таких выражениях из выражения взятия адреса можно вычитать (или прибавлять к нему) константное выражение, которое не содержит выражения взятия адреса.  
  
 Если этот оператор применяется к функциям или l-значениям, то результатом является тип указателя (r-значение), производный от типа операнда. Например, если операнд имеет тип `char`, то результат выражения будет иметь тип указателя на `char`. Оператор взятия адреса, применяется к **const** или `volatile` объектов, результатом которого является **const** `type` ** \* ** или `volatile` `type` ** \* **, где `type` тип исходного объекта.  
  
 Если оператор взятия адреса применяется к [полное имя](http://msdn.microsoft.com/en-us/3fefb16d-8120-4627-8b3f-3d90fbdcd1df), результат зависит от того *полное имя* указывает статический член. Если да, то результатом является указатель на тип, заданный в определении этого члена. Если элемент не является статическим, результатом является указатель на член *имя* из класса, обозначенного *полное имя класса*. (См. [первичные выражения](../cpp/primary-expressions.md) Дополнительные сведения о *полное имя класса*.) В следующем фрагменте кода показано, как отличается результат в зависимости от того, является ли элемент статическим.  
  
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
  
 Адрес перегруженной функции можно принимать только в том случае, если очевидно, к какой именно версии этой функции привязана ссылка. В разделе [перегрузка функций](function-overloading.md) сведения о том, как получить адрес конкретной перегруженная функция.  
  
 Применение оператора взятия адреса к типу ссылки дает тот же результат, что и применение к объекту, к которому привязана ссылка. Пример:  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="output"></a>Вывод  
  
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
  
## <a name="output"></a>Вывод  
  
```  
25  
```  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Декларатор ссылки lvalue: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Операторы косвенного обращения и адреса операнда](../c-language/indirection-and-address-of-operators.md)

