---
title: 'Оператор address-of: &amp; | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8acd615cb2f05e62019f5076a423ae0f8218815a
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406010"
---
# <a name="address-of-operator-amp"></a>Оператор address-of: &amp;
## <a name="syntax"></a>Синтаксис  
  
```  
& cast-expression  
```  
  
## <a name="remarks"></a>Примечания  
 Унарный оператор взятия адреса (**&**) принимает адрес своего операнда. Операнд оператора взятия адреса может быть либо указателем функции либо l значением, указывающим на объект, не является битовым полем.  
  
 Оператор взятия адреса может применяться только к переменным фундаментального типа или типа структуры, класса или объединения, которые были объявлены в области видимости файла, а также к ссылкам на массив с индексом. В таких выражениях из выражения взятия адреса можно вычитать (или прибавлять к нему) константное выражение, которое не содержит выражения взятия адреса.  
  
 Если этот оператор применяется к функциям или l-значениям, то результатом является тип указателя (r-значение), производный от типа операнда. Например, если операнд имеет тип **char**, результат выражения имеет тип указателя на **char**. Оператор взятия адреса, применяется к **const** или **volatile** объекты, результатом которого является `const type *` или `volatile type *`, где **тип** тип исходного объекта объект.  
  
 Когда оператор address-of применяется к имени, результат зависит от того *полное имя* указывает статический член. Если да, то результатом является указатель на тип, заданный в определении этого члена. Если член не является статическим, результатом является указатель на член *имя* из класса, обозначенного *полного имени класса*. (См. в разделе [основные выражения](../cpp/primary-expressions.md) дополнительную информацию о *полного имени класса*.) В следующем фрагменте кода показано, как отличается результат в зависимости от того, является ли элемент статическим.  
  
```cpp 
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
    int iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 В этом примере выражение `&PTM::fValue` имеет результатом тип `float *`, а не `float PTM::*`, поскольку `fValue` является статическим членом.  
  
 Адрес перегруженной функции можно принимать только в том случае, если очевидно, к какой именно версии этой функции привязана ссылка. См. в разделе [перегрузка функций](function-overloading.md) сведения о том, как получить адрес конкретной перегруженная функция.  
  
 Применение оператора взятия адреса к типу ссылки дает тот же результат, что и применение к объекту, к которому привязана ссылка. Пример:  
  
## <a name="example"></a>Пример  
  
```cpp 
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
  
```Output  
&d equals &rd  
```  
  
 В следующем примере оператор взятия адреса используется для того, чтобы передать указатель в качестве аргумента функции:  
  
```cpp 
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
  
```Output  
25  
```  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Встроенные операторы C++, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Декларатор ссылки lvalue: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Операторы косвенного обращения и адреса операнда](../c-language/indirection-and-address-of-operators.md)