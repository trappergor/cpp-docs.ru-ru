---
title: Предупреждение средств компоновщика LNK4227
ms.date: 11/04/2016
f1_keywords:
- LNK4227
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
ms.openlocfilehash: 7b75cff4f03370951245bde1b485d538ffdb4007
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182946"
---
# <a name="linker-tools-warning-lnk4227"></a>Предупреждение средств компоновщика LNK4227

> предупреждение операции метаданных (*HRESULT*): *warning_message*

Компоновщик обнаружил различия метаданных при слиянии:

- Одна или несколько сборок, на которые выполняется сборка в текущий момент сборки.

- Один или несколько файлов исходного кода в компиляции.

Например, LNK4227 может быть вызвана двумя глобальными функциями с одинаковыми именами, но сведения о параметрах объявляются по-разному (то есть объявления не согласуются во всех компиляндов). Используйте Ildasm. exe/TEXT/МЕТАДАТА *object_file* в каждом obj-файле, чтобы увидеть, как типы различаются.

LNK4227 также используется для сообщения о проблемах, возникающих в другом средстве. Найдите предупреждающее сообщение, чтобы получить дополнительные сведения.

Чтобы устранить это предупреждение, необходимо устранить проблемы с метаданными.

## <a name="example"></a>Пример

LNK4227 создается, когда сборка, на которую указывает ссылка, была подписана иначе, чем сборка, ссылающаяся на нее.

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

LNK4227 также может создаваться, когда номера версий в неправильном формате передаются в атрибуты сборки.  Нотация "*" характерна для `AssemblyVersionAttribute`.  Чтобы устранить это предупреждение, используйте только числа в атрибутах версии, кроме `AssemblyVersionAttribute`.

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
