---
title: "Оператор reinterpret_cast | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- reinterpret_cast
- reinterpret_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 71218dc713b24669dc1648b748a0326da0c03152
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="reinterpretcast-operator"></a>Оператор reinterpret_cast
Позволяет преобразовывать любой указатель в указатель любого другого типа. Также позволяет преобразовывать любой целочисленный тип в любой тип указателя и наоборот.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>Примечания  
 Неправильное использование оператора `reinterpret_cast` легко может оказаться небезопасным. Если требуемое преобразование не является низкоуровневым по самой своей природе, следует использовать один из других операторов приведения типов.  
  
 Оператор `reinterpret_cast` можно использовать для таких преобразований, как `char*` в `int*` или `One_class*` в `Unrelated_class*`, которые небезопасны по самой своей сути.  
  
 Результат применения `reinterpret_cast` не может безопасно использоваться ни для чего другого, кроме приведения обратно в исходный тип. Другие применения в лучшем случае будут непереносимыми.  
  
 `reinterpret_cast` Оператор не может удалять **const**, `volatile`, или **__unaligned** атрибуты. В разделе [оператор const_cast](../cpp/const-cast-operator.md) сведения об удалении этих атрибутов.  
  
 Оператор `reinterpret_cast` преобразует значение пустого указателя в значение пустого указателя конечного типа.  
  
 Одним из практических применений оператора `reinterpret_cast` является хэш-функция, которая сопоставляет значение индексу таким образом, что два несовпадающих значения редко соответствуют одинаковым индексам.  
  
```  
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 Оператор `reinterpret_cast` позволяет использовать указатель как целочисленный тип. Затем для получения уникального индекса (уникального с высокой степенью вероятности) к результату применяется побитовый сдвиг и операция XOR с самим собой. Далее индекс усекается с использованием стандартного для языка C приведения к типу возвращаемого значения функции.  
  
## <a name="see-also"></a>См. также  
 [Операторы приведения](../cpp/casting-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
