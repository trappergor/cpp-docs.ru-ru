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
ms.openlocfilehash: aaa07373b7dd22807290ceefa9197b4013c61fe5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778238"
---
# <a name="using-c-interop-implicit-pinvoke"></a>Использование взаимодействия языка C++ (неявный PInvoke)

В отличие от других языков .NET, Visual C++ поддерживает взаимодействие, позволяющий управляемым и неуправляемым кодом, должно существовать в одном приложении и даже в том же файле (с [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы pragma). Это позволяет разработчикам Visual C++ интегрировать функциональность .NET в существующие приложения Visual C++, не нарушая остальной части приложения.

Можно также вызвать неуправляемых функций из управляемого объекта компиляции с помощью [dllexport, dllimport](../cpp/dllexport-dllimport.md).

Неявный PInvoke полезен в тех случаях, когда необходимо указать способ маршалинга параметров функции или какие-либо другие сведения, которые могут быть указаны при явном вызове DllImportAttribute.

Visual C++ предоставляет два способа для управляемых и неуправляемых функций взаимодействия:

- [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Явного вызова PInvoke поддерживается платформой .NET Framework и доступна в большинстве языков .NET. Но как и предполагает его имя, взаимодействия C++ в Visual C++.

## <a name="c-interop"></a>взаимодействие C++

Так как он обеспечивает более высокую безопасность типов, обычно меньше усилий на реализацию, более многое прощает, если неуправляемый интерфейс API будет изменен и позволяет улучшать производительность, не поддерживаемых в средстве явное взаимодействия C++ предпочтительнее явного вызова PInvoke PInvoke. Тем не менее взаимодействия C++ не поддерживается, если неуправляемый исходный код недоступен.

## <a name="c-com-interop"></a>COM-взаимодействие в C++

При взаимодействии с компонентами COM, возможности взаимодействия, поддерживаемые Visual C++ имеют определенное преимущество над другими языками .NET. Не ограничиваясь ограничения платформы .NET Framework [Tlbimp.exe (программа импорта библиотек типов)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), таких как ограниченная поддержка типов данных и обязательное предоставление всех членов интерфейса COM, взаимодействие C++ позволяет COM компоненты к адресу будут и не требует отдельной сборки взаимодействия. В отличие от Visual Basic и C#, Visual C++ можно использовать COM-объекты, непосредственно с помощью обычных механизмов COM (такие как **CoCreateInstance** и **QueryInterface**). Это возможно из-за особенностей взаимодействия C++, которые компилятор автоматически вставлять код преобразования переместиться из управляемого в неуправляемый функций и обратно.

Использование взаимодействия языка C++, COM-компоненты можно использовать как обычно они используются, или они могут заключаться в классы C++. Эти классы-оболочки называются вызываемых оболочек времени выполнения пользовательского или CRCW они имеют два преимущества по сравнению с использованием COM непосредственно в код приложения:

- Результирующий класс может использоваться в языках, отличных от Visual C++.

- Сведения о COM-интерфейса могут быть скрыты от клиентского управляемого кода. Типы данных .NET может использоваться вместо собственных типов и сведения о маршалинге данных может выполняться прозрачно внутри Маршалирование.

Независимо от того, является ли COM используется напрямую или через Маршалирование необходимо выполнить маршалинг типов аргументов, отличных от простой, преобразуемые типы.

## <a name="blittable-types"></a>Преобразуемые типы

Для неуправляемых API, которые используют простые, встроенные типы (см. в разделе [непреобразуемые и преобразуемые типы](/dotnet/framework/interop/blittable-and-non-blittable-types)), специальный код не является обязательным, поскольку эти типы данных имеют одинаковое представление в памяти, но требуют более сложными типами данных маршалинг явного данных. Пример см. в статье [Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода, с помощью PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).

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

## <a name="in-this-section"></a>В этом разделе

- [Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C++](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалирование строк Юникод с использованием взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалирование строк СОМ с использованием взаимодействия C++](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалирование структур с помощью взаимодействия C++](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [Практическое руководство. Маршалирование массивов с помощью взаимодействия C++](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [Практическое руководство. Маршалирование обратных вызовов и делегатов с помощью взаимодействия C++](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [Практическое руководство. Маршалирование встроенных указателей с помощью взаимодействия C++](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [Практическое руководство. Доступ к символам объекта System::String](../dotnet/how-to-access-characters-in-a-system-string.md)

- [Практическое руководство. Преобразование строки char * в массив System::Byte](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [Практическое руководство. Преобразование типа System::String к wchar_t * или char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Практическое руководство. Преобразование строки System::String в стандартную строку](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Практическое руководство. Преобразование стандартной строки в System::String](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Практическое руководство. Получение указателя на массив байтов](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Практическое руководство. Загрузка неуправляемых ресурсов в массив байтов](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Практическое руководство. Изменение ссылочного класса в собственной функции](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Практическое руководство. Машинный код или среда CLR: определение цели созданного образа](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Практическое руководство. Добавление собственной библиотеки DLL в глобальный кэш сборок](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Практическое руководство. Хранение ссылки на тип значения в собственном типе](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Практическое руководство. Хранение ссылки на объект в неуправляемой памяти](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Практическое руководство. Обнаружение компиляции/CLR](../dotnet/how-to-detect-clr-compilation.md)

- [Практическое руководство. Преобразование между классами System::Guid и _GUID](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Практическое руководство. Определение выходного параметра](../dotnet/how-to-specify-an-out-parameter.md)

- [Практическое руководство. Использование собственного типа в компиляции/CLR](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md)

- [Практическое руководство. Создание программы-оболочки собственного класса для использования в C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Сведения об использовании делегатов в сценарии взаимодействий см. в разделе [delegate (расширения компонентов C++)](../extensions/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>См. также

- [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)
