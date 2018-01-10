---
title: "Оператор const_cast | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: const_cast_cpp
dev_langs: C++
helpviewer_keywords: const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79c4aa00038f2d4d7e5cc3d1c86d2e28c6d44229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="constcast-operator"></a>Оператор const_cast
Удаляет **const**, `volatile`, и **__unaligned** атрибуты из класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## <a name="remarks"></a>Примечания  
 Указатель на любой тип объекта или указателя на член данных могут быть преобразованы в тип, идентичны за исключением **const**, `volatile`, и **__unaligned** квалификаторы. Для указателей и ссылок результат будет указывать на исходный объект. Для указателей на данные-члены результат будет указывать на тот же член, что и исходный указатель (uncast) на данные-член. В зависимости от типа объекта, на который осуществляется ссылка, операция записи с помощью результирующего указателя, ссылки или указателя на данные-член может привести к неопределенному поведению.  
  
 Оператор `const_cast` невозможно использовать для непосредственного переопределения постоянного состояния константной переменной.  
  
 Оператор `const_cast` преобразует значение пустого указателя в значение пустого указателя конечного типа.  
  
## <a name="example"></a>Пример  
  
```  
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
  
 В строке, содержащей оператор `const_cast`, тип данных указателя `this` — `const CCTest *`. Оператор `const_cast` изменяет тип данных указателя `this` на `CCTest *`, разрешая изменение члена `number`. Приведение выполняется только для оставшейся части оператора, в котором оно указано.  
  
## <a name="see-also"></a>См. также  
 [Операторы приведения](../cpp/casting-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)