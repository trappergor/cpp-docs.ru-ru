---
title: Класс invalid_argument
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::invalid_argument
helpviewer_keywords:
- invalid_argument class
ms.assetid: af6c227d-ad7c-4e63-9dee-67af81d83506
ms.openlocfilehash: e6b56e98a1adc7426fe0d1b65d623549a4391c8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528951"
---
# <a name="invalidargument-class"></a>Класс invalid_argument

Этот класс служит базовым классом для всех исключений, создаваемых для сообщения о недопустимом аргументе.

## <a name="syntax"></a>Синтаксис

```cpp
class invalid_argument : public logic_error {
public:
    explicit invalid_argument(const string& message);

    explicit invalid_argument(const char *message);

};
```

## <a name="remarks"></a>Примечания

Значение, возвращаемое [what](../standard-library/exception-class.md), — это копия **данных**`.`[сообщения](../standard-library/basic-string-class.md#data).

## <a name="example"></a>Пример

```cpp
// invalid_arg.cpp
// compile with: /EHsc /GR
#include <bitset>
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      bitset< 32 > bitset( string( "11001010101100001b100101010110000") );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught invalid bitset<N> char
Type class std::invalid_argument
*/
```

## <a name="requirements"></a>Требования

**Заголовок:** \<stdexcept>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс logic_error](../standard-library/logic-error-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
