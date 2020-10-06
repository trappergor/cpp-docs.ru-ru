---
title: 'Оператор взятия адреса: &amp;'
description: Оператор взятия адреса языка C++.
ms.date: 10/02/2020
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 8ef7ad065281e4de58ddbdebea25950f8eb9dd06
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765285"
---
# <a name="address-of-operator-amp"></a>Оператор взятия адреса: &amp;

## <a name="syntax"></a>Синтаксис

> **`&`** *`cast-expression`*

## <a name="remarks"></a>Remarks

Унарный оператор взятия адреса ( **`&`** ) принимает адрес своего операнда. Операнд оператора взятия адреса может быть либо указателем функции, либо l-значением, обозначающим объект, который не является битовым полем.

Оператор взятия адреса можно применять только к переменным типов фундаментальных, структурных, классов или объединений, объявленных на уровне области файла, или на ссылки на массивы в индексах. В этих выражениях константное выражение, которое не включает оператор взятия адреса, можно добавлять в выражение address-of или вычитать из него.

Если этот оператор применяется к функциям или l-значениям, то результатом является тип указателя (r-значение), производный от типа операнда. Например, если операнд имеет тип **`char`** , результат выражения будет иметь тип pointer, равный **`char`** . Оператор взятия адреса, примененный к **`const`** **`volatile`** объектам или, принимает значение `const type *` или `volatile type *` , где `type` — Тип исходного объекта.

Адрес перегруженной функции может быть получен только в том случае, если ясно, какая версия функции упоминается. Сведения о получении адреса определенной перегруженной функции см. в разделе [Перегрузка функции](function-overloading.md) .

Если оператор взятия адреса применяется к полному имени, результат зависит от того, указывает ли *полное имя* на статический член. Если да, то результатом является указатель на тип, заданный в определении этого члена. Для элемента, который не является статическим, результатом является указатель на *имя* члена класса, обозначенного *полным именем класса*. Дополнительные сведения о *квалифицированном имени класса*см. в разделе [основные выражения](../cpp/primary-expressions.md).

## <a name="example-address-of-static-member"></a>Пример: адрес статического члена

В следующем фрагменте кода показано, каким образом результат оператора взятия адреса отличается в зависимости от того, является ли член класса статическим:

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

## <a name="example-address-of-a-reference-type"></a>Пример: адрес ссылочного типа

Применение оператора взятия адреса к типу ссылки дает тот же результат, что и применение к объекту, к которому привязана ссылка. Пример:

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

```Output
&d equals &rd
```

## <a name="example-function-address-as-parameter"></a>Пример. адрес функции в качестве параметра

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

```Output
25
```

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы, приоритет и ассоциативность C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Декларатор ссылки Lvalue: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Операторы косвенного обращения и адреса](../c-language/indirection-and-address-of-operators.md)
