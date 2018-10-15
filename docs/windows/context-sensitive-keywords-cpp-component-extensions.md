---
title: Контекстные ключевые слова (C + +/ CLI и C + +/ CX) | Документация Майкрософт
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal_CPP
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d02939e61da4a247b46da5637c38d01e7990c49
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327938"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Контекстные ключевые слова (C + +/ CLI и C + +/ CX)

*Контекстные ключевые слова* — это языковые элементы, которые распознаются только в определенных контекстах. Вне указанного контекста они могут быть символами, которые определяются пользователем.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="remarks"></a>Примечания

Ниже приведен список контекстно-зависимых ключевых слов:

- [abstract](../windows/abstract-cpp-component-extensions.md)

- [delegate](../windows/delegate-cpp-component-extensions.md)

- [event](../windows/event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each, in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [literal](../windows/literal-cpp-component-extensions.md)

- [override](../windows/override-cpp-component-extensions.md)

- [свойство](../windows/property-cpp-component-extensions.md)

- [sealed](../windows/sealed-cpp-component-extensions.md)

- `where` (частью [универсальные шаблоны](../windows/generics-cpp-component-extensions.md))

Для повышения удобочитаемости можно ограничить использование контекстно-зависимые ключевые слова как символы, определяемые пользователем.

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

В следующем примере кода показано, что в соответствующем контексте **свойство** контекстно-зависимые ключевое слово может использоваться для определения свойства и переменной.

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

[Расширения компонентов для .NET и универсальной платформы Windows](../windows/component-extensions-for-runtime-platforms.md)