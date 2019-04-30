---
title: Предупреждение компилятора (уровень 1) C4462
ms.date: 10/25/2017
f1_keywords:
- C4462
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
ms.openlocfilehash: bd4d5c1fd7dd8d7419fc901149ceab7e769e7076
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404056"
---
# <a name="compiler-warning-level-1-c4462"></a>Предупреждение компилятора (уровень 1) C4462

> невозможно определить GUID типа. Программа может завершиться ошибкой во время выполнения.

Предупреждение C4462 возникает в приложении или компоненте среды выполнения Windows, когда открытый `TypedEventHandler` содержит в качестве одного из своих параметров типа ссылку на включающий класс.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4462 в предупреждение уровня 4, добавьте следующую строку в файле исходного кода:

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>Пример

В этом примере возникает предупреждение C4462:

```cpp
namespace N
{
    public ref struct EventArgs sealed {};
    public ref struct R sealed
    {
        R() {}
        event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
    };
}

[Platform::MTAThread]
int main()
{
    auto x = ref new N::R();
}
```

Существует два способа устранения этой ошибки. Одним из способов, который показан в следующем примере, является предоставление событию внутренней доступности, чтобы оно было доступно коду в этом же исполняемом файле, но не в коде других компонентов среды выполнения Windows.

```cpp
internal:
    event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
```

Если событие должно быть открытым, можно использовать другое решение, заключающееся в предоставлении доступа через интерфейс по умолчанию:

```cpp
ref struct R;
public interface struct IR{ event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;};

public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR
{
    R() {}
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
};
```

Идентификатор GUID типа `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^` используется только при обращении к этому типу из другого компонента. Первый способ работает, поскольку после исправления доступ возможен только из собственного компонента. В противном случае компилятор должен предположить наихудший случай и выдать предупреждение.
