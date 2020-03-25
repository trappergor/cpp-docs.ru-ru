---
title: Оператор reinterpret_cast
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 34c2fcb0e1f7f4df4e207d1737afc9c42e011feb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188289"
---
# <a name="reinterpret_cast-operator"></a>Оператор reinterpret_cast

Позволяет преобразовывать любой указатель в указатель любого другого типа. Также позволяет преобразовывать любой целочисленный тип в любой тип указателя и наоборот.

## <a name="syntax"></a>Синтаксис

```
reinterpret_cast < type-id > ( expression )
```

## <a name="remarks"></a>Remarks

Неправильное использование оператора **reinterpret_cast** может быть ненадежным. Если требуемое преобразование не является низкоуровневым по самой своей природе, следует использовать один из других операторов приведения типов.

Оператор **reinterpret_cast** можно использовать для таких преобразований, как `char*`, в `int*`или `One_class*` в `Unrelated_class*`, которые по своей природе являются небезопасными.

Результат **reinterpret_cast** нельзя безопасно использовать ни для чего-либо, кроме приведения обратно к исходному типу. Другие применения в лучшем случае будут непереносимыми.

Оператор **reinterpret_cast** не может приводить к атрибутам **const**, **volatile**или **__unaligned** . Сведения об удалении этих атрибутов см. в разделе [оператор const_cast](../cpp/const-cast-operator.md) .

Оператор **reinterpret_cast** преобразует нулевое значение указателя в значение указателя null целевого типа.

Одним из практических способов использования **reinterpret_cast** является хэш-функция, которая сопоставляет значение с индексом таким образом, чтобы два разных значения редко применялись к одному и тому же индексу.

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

**Reinterpret_cast** позволяет обрабатывать указатель как целочисленный тип. Затем для получения уникального индекса (уникального с высокой степенью вероятности) к результату применяется побитовый сдвиг и операция XOR с самим собой. Далее индекс усекается с использованием стандартного для языка C приведения к типу возвращаемого значения функции.

## <a name="see-also"></a>См. также раздел

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
