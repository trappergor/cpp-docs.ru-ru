---
title: Исключение bad_typeid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9cc93ab5a0f2d7fce12e926d571881ccb9c070fd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092210"
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