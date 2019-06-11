---
title: Контекстно-зависимые ключевые слова (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: ca289a7ebd4578d5c67bb5d3e403d2a9a2756520
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516129"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Контекстно-зависимые ключевые слова (C++/CLI и C++/CX)

*Контекстно-зависимые ключевые слова* — элементы языка, которые имеют определенное значение в конкретном контексте. Вне указанного контекста они могут быть символами, которые определяются пользователем.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="remarks"></a>Примечания

Ниже приведен список контекстно-зависимых ключевых слов:

- [abstract](abstract-cpp-component-extensions.md)

- [delegate](delegate-cpp-component-extensions.md)

- [event](event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each, in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [literal](literal-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [свойство](property-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- `where` (часть [универсальных шаблонов](generics-cpp-component-extensions.md))

Для повышения удобочитаемости можно ограничить использование контекстно-зависимых ключевых слов в качестве символов, определяемых пользователем.

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для данной возможности в рамках этой платформы).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для данной возможности в рамках этой платформы).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода показано, что в соответствующем контексте контекстно-зависимое ключевое слово **property** можно использовать для определения свойства и переменной.

```cpp
// context_sensitive_keywords.cpp
// compile with: /clr
public ref class C {
   int MyInt;
public:
   C() : MyInt(99) {}

   property int Property_Block {   // context-sensitive keyword
      int get() { return MyInt; }
   }
};

int main() {
   int property = 0;               // variable name
   C ^ MyC = gcnew C();
   property = MyC->Property_Block;
   System::Console::WriteLine(++property);
}
```

```Output
100
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)