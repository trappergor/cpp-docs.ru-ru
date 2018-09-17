---
title: Класс bad_alloc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- new/std::bad_alloc
dev_langs:
- C++
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 571885410363aee55d15e68b81ba4fd9e2b8e54b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705592"
---
# <a name="badalloc-class"></a>Класс bad_alloc

Данный класс описывает исключение, возникновение которого указывает на то, что запрос на выделение памяти не выполнен.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_alloc : public exception {
    bad_alloc();
virtual ~bad_alloc();

};
```

## <a name="remarks"></a>Примечания

Значение, возвращенное `what` является строка C определяемого реализацией. Ни одна из функций-членов не создает исключение.

## <a name="requirements"></a>Требования

**Заголовок:** \<new>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
// bad_alloc.cpp
// compile with: /EHsc
#include<new>
#include<iostream>
using namespace std;

int main() {
   char* ptr;
   try {
      ptr = new char[(~unsigned int((int)0)/2) - 1];
      delete[] ptr;
   }
   catch( bad_alloc &ba) {
      cout << ba.what( ) << endl;
   }
}
```

## <a name="sample-output"></a>Пример результатов выполнения

```Output
bad allocation
```

## <a name="requirements"></a>Требования

**Заголовок:** \<new>

## <a name="see-also"></a>См. также

[Класс exception](../standard-library/exception-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
