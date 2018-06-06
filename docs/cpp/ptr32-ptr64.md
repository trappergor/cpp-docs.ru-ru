---
title: __ptr32 __ptr64 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5746c8f54a51e24bad23dcb66f6648266e2e4b56
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704819"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Блок, относящийся только к системам Microsoft**

`__ptr32` представляет собственный указатель в 32-разрядной системе, а `__ptr64` представляет собственный указатель в 64-разрядной системе.

В следующем примере показано, как объявить каждый из этих типов указателей.

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

 В 32-разрядной системе указатель, объявленный с помощью `__ptr64`, усекается до 32-разрядного указателя. В 64-разрядной системе указатель, объявленный с помощью `__ptr32`, приводится к 64-разрядному указателю.

> [!NOTE]
> Нельзя использовать `__ptr32` или `__ptr64` при компиляции с параметром **/CLR: pure**. В противном случае создается ошибка компилятора C2472. **/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

## <a name="example"></a>Пример

В следующем примере показано, как объявить и выделить указатели с ключевыми словами `__ptr32` и `__ptr64`.

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

- [Фундаментальные типы](../cpp/fundamental-types-cpp.md)