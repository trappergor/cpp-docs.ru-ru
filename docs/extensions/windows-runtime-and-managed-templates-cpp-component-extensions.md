---
title: Среда выполнения Windows и управляемые шаблоны (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
ms.openlocfilehash: 5765370e611e5822b3b2d156d2eee5d21e5b453d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376308"
---
# <a name="windows-runtime-and-managed-templates-ccli-and-ccx"></a>Среда выполнения Windows и управляемые шаблоны (C++/CLI и C++/CX)

Шаблоны позволяют определять прототип среды выполнения Windows или тип среды CLR, а затем создавать варианты этого типа с помощью разных параметров типа шаблонов.

## <a name="all-runtimes"></a>Все среды выполнения

Шаблоны можно создавать из типов значений и ссылочных типов.  Дополнительные сведения о создании типов значений и ссылочных типов см. в статье [ref class и ref struct (C++/CLI и C++/CX)](classes-and-structs-cpp-component-extensions.md).

Дополнительные сведения о стандартных шаблонах классов C++ см. в статье [Class Templates](../cpp/class-templates.md) (Шаблоны классов).

## <a name="windows-runtime"></a>Среда выполнения Windows

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

На создание шаблонов класса из управляемых типов существует несколько ограничений, которые показаны в следующих примерах кода.

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

Экземпляр универсального типа можно создать с помощью параметра шаблона управляемого типа, но создать экземпляр управляемого шаблона с помощью параметра шаблона универсального типа невозможно. Это связано с тем, что универсальные типы разрешаются во время выполнения. Дополнительные сведения см. в статье [Универсальные и обычные шаблоны (C++/CLI)](generics-and-templates-visual-cpp.md).

```cpp
// managed_templates.cpp
// compile with: /clr /c

generic<class T>
ref class R;

template<class T>
ref class Z {
   // Instantiate a generic with a template parameter.
   R<T>^ r;    // OK
};

generic<class T>
ref class R {
   // Cannot instantiate a template with a generic parameter.
   Z<T>^ z;   // C3231
};
```

Универсальный тип или функция не могут быть вложены в управляемый шаблон.

```cpp
// managed_templates_2.cpp
// compile with: /clr /c

template<class T> public ref class R {
   generic<class T> ref class W {};   // C2959
};
```

Доступ с помощью синтаксиса языка C++/CLI к шаблонам, определенным в сборке, на которую существует ссылка, получить нельзя, но можно использовать отражение. Если шаблон не мгновенно, он не испускается в метаданных. При создании экземпляра шаблона в метаданных появляются только функции-члены, на которые существуют ссылки.

```cpp
// managed_templates_3.cpp
// compile with: /clr

// Will not appear in metadata.
template<class T> public ref class A {};

// Will appear in metadata as a specialized type.
template<class T> public ref class R {
public:
   // Test is referenced, will appear in metadata
   void Test() {}

   // Test2 is not referenced, will not appear in metadata
   void Test2() {}
};

// Will appear in metadata.
generic<class T> public ref class G { };

public ref class S { };

int main() {
   R<int>^ r = gcnew R<int>;
   r->Test();
}
```

Управляемый модификатор класса можно изменить в частичной или явной специализации шаблона класса.

```cpp
// managed_templates_4.cpp
// compile with: /clr /c

// class template
// ref class
template <class T>
ref class A {};

// partial template specialization
// value type
template <class T>
value class A <T *> {};

// partial template specialization
// interface
template <class T>
interface class A<T%> {};

// explicit template specialization
// native class
template <>
class A <int> {};
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
