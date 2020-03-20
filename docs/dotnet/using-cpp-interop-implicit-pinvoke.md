---
title: Использование взаимодействия языка C++ (неявный PInvoke)
ms.date: 11/04/2016
helpviewer_keywords:
- blittable types [C++]
- platform invoke [C++], implicit
- interop [C++], features
- data marshaling [C++], C++ Interop features
- porting [C++], C++ native to .NET
- COM interfaces [C++]
- implicit platform invoke
- examples [C++], interoperability
- types [C++], blittable
- marshaling [C++], C++ Interop features
- platform invoke [C++], examples
- interoperability [C++]
- C++ Interop
- interoperability [C++], Implicit PInvoke
- C++, interop
- C++ COM Interop
- .NET [C++], porting C++ native to
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
ms.openlocfilehash: d26fbefd87b3ba6d6ca7e183be78608777f383b5
ms.sourcegitcommit: 27d9db019f6d84c94de9e6aff0170d918cee6738
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2020
ms.locfileid: "79545423"
---
# <a name="using-c-interop-implicit-pinvoke"></a>Использование взаимодействия языка C++ (неявный PInvoke)

В отличие от других языков .NET, C++ визуальный элемент имеет поддержку взаимодействия, которая позволяет управляемому и неуправляемому коду существовать в том же приложении и даже в одном файле (с [управляемыми неуправляемыми](../preprocessor/managed-unmanaged.md) директивами pragma). Это позволяет визуальным C++ разработчикам интегрировать функциональность .NET в существующие C++ визуальные приложения, не нарушая остальную часть приложения.

Вы также можете вызывать неуправляемые функции из управляемого компилируемого объекта с помощью [dllexport, dllimport](../cpp/dllexport-dllimport.md).

Неявный PInvoke полезен, если не нужно указывать способ маршалирования параметров функции или какие-либо другие сведения, которые можно указать при явном вызове DllImportAttribute.

Визуальный C++ элемент предоставляет два способа взаимодействия управляемых и неуправляемых функций:

- [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Явный вызов PInvoke поддерживается .NET Framework и доступен в большинстве языков .NET. Но, как и предполагает его C++ имя, взаимодействие характерно C++для визуального элемента.

## <a name="c-interop"></a>взаимодействие C++

C++Взаимодействие обеспечивает лучшую безопасность типов, и его реализация обычно менее утомительна. Однако взаимодействие C++ не является вариантом, если неуправляемый исходный код недоступен или для межплатформенных проектов.

## <a name="c-com-interop"></a>COM-взаимодействие в C++

Функции взаимодействия, поддерживаемые визуальным C++ компонентом, предлагают определенные преимущества по сравнению с другими языками .NET, когда речь идет о взаимодействии с COM-компонентами. Вместо того чтобы ограничиваться ограничениями .NET Framework [Tlbimp. exe (средства импорта библиотек типов)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), например ограниченной поддержки типов данных и обязательной раскрытия каждого члена каждого COM-интерфейса, C++ взаимодействие позволяет получить доступ к COM-компонентам в службах и не требует отдельных сборок взаимодействия. В отличие от Visual Basic C#и, C++ Visual может использовать COM-объекты непосредственно с помощью обычных механизмов com (таких как **CoCreateInstance** и **QueryInterface**). Это возможно из-за C++ функций взаимодействия, которые приводят к тому, что компилятор автоматически вставляет код перехода из управляемой функции в неуправляемую и обратно.

С C++ помощью взаимодействия можно использовать COM-компоненты, так как они обычно используются или могут быть заключены C++ в классы. Эти классы-оболочки называются пользовательскими вызываемыми оболочками времени выполнения или Крквс. они имеют два преимущества по сравнению с использованием COM непосредственно в коде приложения:

- Итоговый класс можно использовать на языках, отличных от C++Visual.

- Сведения о COM-интерфейсе могут быть скрыты из управляемого кода клиента. Типы данных .NET могут использоваться вместо собственных типов, а сведения о маршалировании данных могут быть прозрачно выполнены внутри КРКВ.

Независимо от того, используется ли COM напрямую или через КРКВ, необходимо маршалировать типы аргументов, Кроме простых, преобразуемых типов.

## <a name="blittable-types"></a>Непреобразуемые типы

Для неуправляемых интерфейсов API, использующих простые встроенные типы (см. раздел непреобразуемые [и непреобразуемые типы](/dotnet/framework/interop/blittable-and-non-blittable-types)), специальное кодирование не требуется, так как эти типы данных имеют одинаковое представление в памяти, но более сложные типы данных требуют явного маршалирования данных. Пример см. в разделе [как вызывать собственные библиотеки DLL из управляемого кода с помощью PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).

## <a name="example"></a>Пример

```cpp
// vcmcppv2_impl_dllimp.cpp
// compile with: /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

// Implicit DLLImport specifying calling convention
extern "C" int __stdcall MessageBeep(int);

// explicit DLLImport needed here to use P/Invoke marshalling because
// System::String ^ is not the type of the first parameter to printf
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]
// or just
// [DllImport("msvcrt.dll")]
int printf(System::String ^, ...);

int main() {
   // (string literals are System::String by default)
   printf("Begin beep\n");
   MessageBeep(100000);
   printf("Done\n");
}
```

```Output
Begin beep
Done
```

## <a name="in-this-section"></a>в этом разделе

- [Практическое руководство. Маршалинг строк ANSI с использованием взаимодействия C++](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалинг строк Юникода с использованием взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалинг строк COM с помощью взаимодействия C++](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалинг структур с помощью взаимодействия C++](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [Практическое руководство. Маршалинг массивов с помощью взаимодействия C++](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [Практическое руководство. Маршалинг обратных вызовов и делегатов посредством взаимодействия C++](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [Практическое руководство. Маршалинг встроенных указателей посредством взаимодействия C++](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [Практическое руководство. Доступ к символам объекта System::String](../dotnet/how-to-access-characters-in-a-system-string.md)

- [Практическое руководство. Преобразование строки char * в массив System::Byte](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [Как преобразовать строку System:: String в wchar_t * или char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Практическое руководство. Преобразование строки System::String в стандартную строку](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Практическое руководство. Преобразование стандартной строки к типу System::String](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Практическое руководство. Получение указателя на массив байтов](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Практическое руководство. Загрузка неуправляемых ресурсов в массив байтов](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Практическое руководство. Изменение ссылочного класса в собственной функции](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Практическое руководство. Машинный код или среда CLR: определение цели созданного образа](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Практическое руководство. Добавление машинной библиотеки DLL в глобальный кэш сборок](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Практическое руководство. Сохранение ссылки на тип значения в собственном типе](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Практическое руководство. Хранение ссылки на объект в неуправляемой памяти](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Как обнаруживать компиляцию/CLR](../dotnet/how-to-detect-clr-compilation.md)

- [Практическое руководство. Преобразование между классами System::Guid и _GUID](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Практическое руководство. Определение выходного параметра](../dotnet/how-to-specify-an-out-parameter.md)

- [Как использовать машинный тип в компиляции/clr](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md)

- [Практическое руководство. Создание программы-оболочки собственного класса для использования в C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Сведения об использовании делегатов в сценарии взаимодействия см. в разделе [DelegateC++ (расширения компонентов)](../extensions/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>См. также:

- [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)
