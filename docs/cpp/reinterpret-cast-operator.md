---
title: Оператор reinterpret_cast
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 421a1fdce6834f800cd33a55d75c9dc4f88ffc93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463102"
---
# <a name="reinterpretcast-operator"></a>Оператор reinterpret_cast

Позволяет преобразовывать любой указатель в указатель любого другого типа. Также позволяет преобразовывать любой целочисленный тип в любой тип указателя и наоборот.

## <a name="syntax"></a>Синтаксис

```
reinterpret_cast < type-id > ( expression )
```

## <a name="remarks"></a>Примечания

Неправильное использование **reinterpret_cast** оператор легко может оказаться небезопасным. Если требуемое преобразование не является низкоуровневым по самой своей природе, следует использовать один из других операторов приведения типов.

**Reinterpret_cast** оператор может использоваться для выполнения преобразований, таких как `char*` для `int*`, или `One_class*` для `Unrelated_class*`, которые небезопасны.

Результат **reinterpret_cast** не может безопасно использоваться ни для чего другого, кроме приведения обратно к его исходному типу. Другие применения в лучшем случае будут непереносимыми.

**Reinterpret_cast** оператор не может удалять **const**, **volatile**, или **__unaligned** атрибуты. См. в разделе [оператор const_cast](../cpp/const-cast-operator.md) сведения об удалении этих атрибутов.

**Reinterpret_cast** оператор преобразует значение пустого указателя в значение пустого указателя конечного типа.

Одним из практических применений из **reinterpret_cast** находится в хэш-функции, которая сопоставляет значение индексу таким образом, что два несовпадающих значения редко соответствуют одинаковым индексам.

```cpp
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

**Reinterpret_cast** позволяет использовать указатель должен обрабатываться как целочисленный тип. Затем для получения уникального индекса (уникального с высокой степенью вероятности) к результату применяется побитовый сдвиг и операция XOR с самим собой. Далее индекс усекается с использованием стандартного для языка C приведения к типу возвращаемого значения функции.

## <a name="see-also"></a>См. также

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)