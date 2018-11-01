---
title: Исключение bad_typeid
ms.date: 11/04/2016
f1_keywords:
- bad_typeid
- bad_typeid_cpp
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
ms.openlocfilehash: 5d53d2e25b56aa78edaebcd4be0e468993ebb8f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514040"
---
# <a name="badtypeid-exception"></a>Исключение bad_typeid

**Bad_typeid** исключение [оператор typeid](../cpp/typeid-operator.md) при операнд для **typeid** является указателем NULL.

## <a name="syntax"></a>Синтаксис

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>Примечания

Интерфейс для **bad_typeid** является:

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();
};
```

В следующем примере показан **typeid** оператор генерации **bad_typeid** исключение.

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo.h>
#include <iostream>

class A{
public:
   // object for class needs vtable
   // for RTTI
   virtual ~A();
};

using namespace std;
int main() {
A* a = NULL;

try {
   cout << typeid(*a).name() << endl;  // Error condition
   }
catch (bad_typeid){
   cout << "Object is NULL" << endl;
   }
}
```

## <a name="output"></a>Вывод

```Output
Object is NULL
```

## <a name="see-also"></a>См. также

[Сведения о типах среды выполнения](../cpp/run-time-type-information.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)