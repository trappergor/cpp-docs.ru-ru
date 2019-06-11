---
title: ref new, gcnew (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
ms.openlocfilehash: f3dd0b73e300b44cb4f35e42683725813453d7de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516649"
---
# <a name="ref-new-gcnew--ccli-and-ccx"></a>ref new, gcnew (C++/CLI и C++/CX)

Агрегатное ключевое слово **ref new** выделяет экземпляр типа, который является мусором, собираемым, когда объект становится недоступным, и возвращает дескриптор ([^](handle-to-object-operator-hat-cpp-component-extensions.md)) выделенному объекту.

## <a name="all-runtimes"></a>Все среды выполнения

Память для экземпляра типа, выделяемая **ref new**, освобождается автоматически.

Операция **ref new** вызывает исключение `OutOfMemoryException`, если не удается выделить память.

Дополнительные сведения о выделении и освобождении памяти для собственных типов C++ см. в статье [Операторы new и delete](../cpp/new-and-delete-operators.md).

## <a name="windows-runtime"></a>Среда выполнения Windows

Используйте **ref new**, чтобы выделить память для объектов среды выполнения Windows, время существования которых требуется администрировать автоматически. Объект автоматически освобождается, когда число ссылок становится равным нулю, что происходит после выхода последней копии ссылки за пределы области. Подробные сведения см. в статье [Ref classes and structs (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md) (Ссылочные классы и структуры (C++/CX)).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

Память для управляемого типа (типа ссылки или значений) выделяется с помощью **gcnew** и освобождается с помощью сборки мусора.

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере с помощью **gcnew** выделяется объект Message.

```cpp
// mcppv2_gcnew_1.cpp
// compile with: /clr
ref struct Message {
   System::String^ sender;
   System::String^ receiver;
   System::String^ data;
};

int main() {
   Message^ h_Message  = gcnew Message;
  //...
}
```

В следующем примере с помощью **gcnew** создается упакованный тип значения для использования в качестве ссылочного типа.

```cpp
// example2.cpp : main project file.
// compile with /clr
using namespace System;
value class Boxed {
    public:
        int i;
};
int main()
{
    Boxed^ y = gcnew Boxed;
    y->i = 32;
    Console::WriteLine(y->i);
    return 0;
}
```

```Output
32
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)