---
title: Предупреждение компилятора (уровень 1) C4462 | Документы Microsoft
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4462
dev_langs:
- C++
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105a78fe9f8a8d2b6442c9b403af0266de53d3b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4462"></a>Предупреждение компилятора (уровень 1) C4462

> невозможно определить GUID типа. Программа может завершиться ошибкой во время выполнения.

Предупреждение C4462 возникает в приложении или компоненте среды выполнения Windows, когда открытый `TypedEventHandler` содержит в качестве одного из своих параметров типа ссылку на включающий класс.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4462 в предупреждение уровня 4, добавьте эту строку в файле исходного кода:

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>Пример

В следующем примере возникает предупреждение C4462:

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
