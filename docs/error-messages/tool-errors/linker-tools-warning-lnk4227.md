---
title: Предупреждение средств компоновщика LNK4227
ms.date: 11/04/2016
f1_keywords:
- LNK4227
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
ms.openlocfilehash: fb657719c69445ce23d36ccf04ac4a14db0955e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352746"
---
# <a name="linker-tools-warning-lnk4227"></a>Предупреждение средств компоновщика LNK4227

> Предупреждение при операции с метаданными (*HRESULT*): *предупреждающее_сообщение*

Компоновщик обнаружены различия в метаданных при слиянии:

- Один или несколько указанных ссылками сборок с идет построение сборки.

- Один или несколько файлов исходного кода при компиляции.

Например, LNK4227 может появиться при наличии двух глобальных функций с одинаковыми именами, но сведения о параметрах, объявленные по-разному (то есть объявления не являются согласованными во всех компилируемых объектах). Используйте ildasm.exe/Text/Metadata *object_file* в каждый OBJ-файл, чтобы увидеть, как типы отличаются.

LNK4227 также позволяет сообщать о проблемах, которые создаются с помощью другого средства. Поиск предупреждающее сообщение, Дополнительные сведения.

Чтобы устранить это предупреждение, необходимо исправить проблемы с метаданными.

## <a name="example"></a>Пример

LNK4227 создается в том случае, когда сборку был подписан иначе, чем сборка, ссылающаяся на нее.

Следующий пример приводит к возникновению ошибки LNK4227:

```cpp
// LNK4227.cpp
// compile with: /clr
using namespace System::Reflection;

[assembly:AssemblyDelaySignAttribute(false)];

int main() {}
```

И потом

```cpp
// LNK4227b.cpp
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe
using namespace System::Reflection;
using namespace System::Runtime::CompilerServices;

[assembly:AssemblyDelaySignAttribute(true)];
// Try the following line instead
// [assembly:AssemblyDelaySignAttribute(false)];

ref class MyClass
{
};
```

## <a name="example"></a>Пример

LNK4227 также может возникать, если атрибуты сборки передаются номера версий в неверном формате.  "*" Нотации относится только к `AssemblyVersionAttribute`.  Чтобы устранить это предупреждение, используйте только числа в атрибуты версии отличное от `AssemblyVersionAttribute`.

Следующий пример приводит к возникновению ошибки LNK4227:

```cpp
// LNK4227e.cpp
// compile with: /clr /LD /W1
using namespace System::Reflection;
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227
// try the following line instead
// [assembly:AssemblyFileVersionAttribute("2.3")];
```