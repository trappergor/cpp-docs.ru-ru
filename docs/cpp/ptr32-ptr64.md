---
title: __ptr32 __ptr64 | Документация Майкрософт
ms.custom: ''
ms.date: 10/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
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
ms.openlocfilehash: 50360ab6a163f70f4f950e44d963b9aa67dc04f4
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161649"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Блок, относящийся только к системам Microsoft**

**__ptr32** представляет собственный указатель в 32-разрядной системе, хотя **__ptr64** представляет собственный указатель в 64-разрядной системе.

В следующем примере показано, как объявить каждый из этих типов указателей.

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

В 32-разрядной системе указатель, объявленный с **__ptr64** усекается до 32-разрядного указателя. В 64-разрядной системе указатель, объявленный с **__ptr32** приводится к 64-разрядного указателя.

> [!NOTE]
> Нельзя использовать **__ptr32** или **__ptr64** при компиляции с параметром **/CLR: pure**. В противном случае будет создаваться Ошибка компилятора C2472. **/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

Для совместимости с предыдущими версиями **_ptr32** и **_ptr64** являются синонимами для **__ptr32** и **__ptr64** Если параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) указан.

## <a name="example"></a>Пример

В следующем примере показано, как объявить и выделить указатели с **__ptr32** и **__ptr64** ключевые слова.

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

[Фундаментальные типы](../cpp/fundamental-types-cpp.md)