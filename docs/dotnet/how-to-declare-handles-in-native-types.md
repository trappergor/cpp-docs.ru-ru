---
title: Практическое руководство. Объявление дескрипторов в собственных типах
ms.custom: get-started-article
ms.date: 11/04/2016
f1_keywords:
- gcroot
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
ms.openlocfilehash: 4b5cd212589be04f5f9f3a5dd6d4496a8f5add2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464932"
---
# <a name="how-to-declare-handles-in-native-types"></a>Практическое руководство. Объявление дескрипторов в собственных типах

Нельзя объявлять тип дескриптора в собственном типе. в файле vcclr.h предоставляет типобезопасную оболочку шаблон `gcroot` для ссылки на объект CLR из кучи C++. Этот шаблон позволяет встраивать виртуальный дескриптор в собственный тип и обрабатывать его так, будто бы это был базовый тип. В большинстве случаев можно использовать `gcroot` объект в качестве встроенного типа без приведения типов. Однако при использовании [для каждого из них в](../dotnet/for-each-in.md), необходимо использовать `static_cast` для получения базовой управляемой ссылки.

`gcroot` Шаблона реализуется с помощью средств значение класса System::Runtime::InteropServices::GCHandle, который предоставляет «маркеры» в куче сбора мусора. Обратите внимание, что сами дескрипторы не собираются и удаляются, когда они больше не используются, деструктором `gcroot` класс (вручную вызвать его нельзя). Если вы создаете экземпляры `gcroot` объекта в неуправляемой куче, необходимо вызвать удаление в этом ресурсе.

Среда выполнения поддерживает связь между дескриптора и объект CLR, который он ссылается. Когда объект CLR перемещается с кучей сборщиком мусора, дескриптор возвращает новый адрес объекта. Переменная не нужно быть закреплен, прежде чем он назначен `gcroot` шаблона.

## <a name="example"></a>Пример

В этом примере показано, как создать `gcroot` объект в собственный стек.

```
// mcpp_gcroot.cpp
// compile with: /clr
#include <vcclr.h>
using namespace System;

class CppClass {
public:
   gcroot<String^> str;   // can use str as if it were String^
   CppClass() {}
};

int main() {
   CppClass c;
   c.str = gcnew String("hello");
   Console::WriteLine( c.str );   // no cast required
}
```

```Output
hello
```

## <a name="example"></a>Пример

В этом примере показано, как создать `gcroot` объекта в неуправляемой куче.

```
// mcpp_gcroot_2.cpp
// compile with: /clr
// compile with: /clr
#include <vcclr.h>
using namespace System;

struct CppClass {
   gcroot<String ^> * str;
   CppClass() : str(new gcroot<String ^>) {}

   ~CppClass() { delete str; }

};

int main() {
   CppClass c;
   *c.str = gcnew String("hello");
   Console::WriteLine( *c.str );
}
```

```Output
hello
```

## <a name="example"></a>Пример

В этом примере показано, как использовать `gcroot` для хранения ссылок на типы значений (не ссылочные типы) в собственном типе с помощью `gcroot` на упакованный тип.

```
// mcpp_gcroot_3.cpp
// compile with: /clr
#include < vcclr.h >
using namespace System;

public value struct V {
   String^ str;
};

class Native {
public:
   gcroot< V^ > v_handle;
};

int main() {
   Native native;
   V v;
   native.v_handle = v;
   native.v_handle->str = "Hello";
   Console::WriteLine("String in V: {0}", native.v_handle->str);
}
```

```Output
String in V: Hello
```

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)