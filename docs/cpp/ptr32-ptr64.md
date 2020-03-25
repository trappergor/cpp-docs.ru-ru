---
title: __ptr32, __ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: c3ebe642284c6ee269dbfc39985630b7d949435f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179215"
---
# <a name="__ptr32-__ptr64"></a>__ptr32, __ptr64

**Блок, относящийся только к системам Microsoft**

**__ptr32** представляет собственный указатель в 32-разрядной системе, а **__ptr64** представляет собственный указатель в 64-разрядной системе.

В следующем примере показано, как объявить каждый из этих типов указателей.

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

В 32-разрядной системе указатель, объявленный с **__ptr64** , усекается до 32-разрядного указателя. В 64-разрядной системе указатель, объявленный с **__ptr32** , приводится к 64-разрядному указателю.

> [!NOTE]
> Нельзя использовать **__ptr32** или **__ptr64** при компиляции с **параметром/clr: pure**. В противном случае будет сформирована ошибка компилятора C2472. Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

Для совместимости с предыдущими версиями **_ptr32** и **_ptr64** являются синонимами для **__ptr32** и **__ptr64** , если только не задан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

## <a name="example"></a>Пример

В следующем примере показано, как объявить и выделить указатели с ключевыми словами **__ptr32** и **__ptr64** .

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

## <a name="see-also"></a>См. также раздел

[Встроенные типы](../cpp/fundamental-types-cpp.md)
