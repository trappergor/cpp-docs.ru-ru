---
title: Оператор const_cast | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89ed2b161c5b8f73d68fb22eb29eb00e057d7029
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944561"
---
# <a name="constcast-operator"></a>Оператор const_cast
Удаляет **const**, **volatile**, и **__unaligned** атрибуты из класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
const_cast <type-id> (expression)  
  
```  
  
## <a name="remarks"></a>Примечания  
 Указатель на объект любого типа или указатель на данные-член можно явно преобразовать в тип, идентичны, за исключением **const**, **volatile**, и **__unaligned** квалификаторы. Для указателей и ссылок результат будет указывать на исходный объект. Для указателей на данные-члены результат будет указывать на тот же член, что и исходный указатель (uncast) на данные-член. В зависимости от типа объекта, на который осуществляется ссылка, операция записи с помощью результирующего указателя, ссылки или указателя на данные-член может привести к неопределенному поведению.  
  
 Оператор `const_cast` невозможно использовать для непосредственного переопределения постоянного состояния константной переменной.  
  
 Оператор `const_cast` преобразует значение пустого указателя в значение пустого указателя конечного типа.  
  
## <a name="example"></a>Пример  
  
```cpp 
// expre_const_cast_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CCTest {  
public:  
   void setNumber( int );  
   void printNumber() const;  
private:  
   int number;  
};  
  
void CCTest::setNumber( int num ) { number = num; }  
  
void CCTest::printNumber() const {  
   cout << "\nBefore: " << number;  
   const_cast< CCTest * >( this )->number--;  
   cout << "\nAfter: " << number;  
}  
  
int main() {  
   CCTest X;  
   X.setNumber( 8 );  
   X.printNumber();  
}  
```  
  
 В строке, содержащей `const_cast`, тип данных **это** указатель находится `const CCTest *`. `const_cast` Оператор изменяет тип данных **это** указатель на `CCTest *`, позволяя член `number` изменяемой. Приведение выполняется только для оставшейся части оператора, в котором оно указано.  
  
## <a name="see-also"></a>См. также  
 [Операторы приведения](../cpp/casting-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)