---
title: Вызов неуправляемых функций из управляемого кода
ms.date: 11/04/2016
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
ms.openlocfilehash: 50f40cc147daaa26a7fa4e607f0d4dd42cf22d61
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545369"
---
# <a name="calling-native-functions-from-managed-code"></a>Вызов неуправляемых функций из управляемого кода

Среда CLR предоставляет службы вызова платформы (PInvoke), которые позволяют управляемому коду вызывать функции в стиле C в собственных динамически связанных библиотеках (DLL). Один и тот же процесс упаковки данных используется для взаимодействия COM со средой выполнения и для механизма «только что работает» или IJW.

Дополнительные сведения см. в разделе:

- [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

В примерах в этом разделе показано, как можно использовать `PInvoke`. `PInvoke` может упростить настраиваемое маршалирование данных, так как сведения о маршалировании можно декларативно использовать в атрибутах вместо написания кода процедурного маршалирования.

> [!NOTE]
>  Библиотека упаковки предоставляет альтернативный способ маршалирования данных между собственными и управляемыми средами оптимизированным способом. Дополнительные сведения о библиотеке упаковки см. [в разделе Общие сведения о маршалировании C++ в](../dotnet/overview-of-marshaling-in-cpp.md) . Библиотека маршалирования может использоваться только для данных, а не для функций.

## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke и атрибут DllImport

В следующем примере показано использование `PInvoke` в визуальной C++ программе. Собственная функция PUT определена в библиотеке msvcrt. dll. Атрибут DllImport используется для объявления PUT.

```cpp
// platform_invocation_services.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", CharSet=CharSet::Ansi)]
extern "C" int puts(String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

Следующий пример эквивалентен предыдущему примеру, но использует IJW.

```cpp
// platform_invocation_services_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#include <stdio.h>

int main() {
   String ^ pStr = "Hello World!";
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();
   puts(pChars);

   Marshal::FreeHGlobal((IntPtr)pChars);
}
```

### <a name="advantages-of-ijw"></a>Преимущества IJW

- Для неуправляемых интерфейсов API, используемых программой, не требуется записывать `DLLImport` объявления атрибутов. Просто включите файл заголовка и ссылку на библиотеку импорта.

- Механизм IJW выполняется немного быстрее (например, заглушкам IJW не нужно проверять, нужно ли закреплять или копировать элементы данных, так как это делается явным образом разработчиком).

- Он ясно иллюстрирует проблемы с производительностью. В данном случае, тот факт, что выполняется перевод из строки Юникода в строку ANSI и имеется возможность выделения и освобождения памяти для помощника. В этом случае разработчик, пишущий код с помощью IJW, осознает, что вызов `_putws` и использование `PtrToStringChars` будет лучше для производительности.

- Если вы вызываете множество неуправляемых API-интерфейсов с помощью одних и тех же данных, маршалирует их один раз и передача упакованной копии гораздо эффективнее, чем повторное маршалирование каждый раз.

### <a name="disadvantages-of-ijw"></a>Недостатки IJW

- Упаковка должна быть явно указана в коде, а не атрибутами (которые часто имеют соответствующие значения по умолчанию).

- Код маршалирования является встроенным, где он более неагрессивен в потоке логики приложения.

- Поскольку API-интерфейсы явного маршалирования возвращают `IntPtr` типов для переноса 32-бит в 64-разрядную переносимость, необходимо использовать дополнительные вызовы `ToPointer`.

Конкретный метод, предоставляемый C++ , является более эффективным, явным методом, за счет некоторой сложности.

Если приложение использует преимущественно неуправляемые типы данных или вызывает больше неуправляемых интерфейсов API, чем .NET Framework API, рекомендуется использовать функцию IJW. Чтобы вызвать случайный неуправляемый API в основном управляемом приложении, этот вариант более незаметен.

## <a name="pinvoke-with-windows-apis"></a>Вызов PInvoke с помощью API-интерфейсов Windows

PInvoke удобно использовать для вызова функций в Windows.

В этом примере визуальная C++ программа взаимодействует с функцией MessageBox, которая является частью API Win32.

```cpp
// platform_invocation_services_4.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
typedef void* HWND;
[DllImport("user32", CharSet=CharSet::Ansi)]
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);

int main() {
   String ^ pText = "Hello World! ";
   String ^ pCaption = "PInvoke Test";
   MessageBox(0, pText, pCaption, 0);
}
```

Выходные данные представляют собой окно сообщения с именем PInvoke Test и содержит текст Hello World!.

Сведения о упаковке также используются PInvoke для поиска функций в библиотеке DLL. В user32. dll на самом деле отсутствует функция MessageBox, но charset = Charset:: ANSI позволяет PInvoke использовать функцию MessageBox, версию ANSI вместо MessageBoxW, которая является версией Юникода. Как правило, рекомендуется использовать версии Юникода неуправляемых интерфейсов API, так как это устраняет нагрузку на перевод из собственного формата Юникода .NET Framework строковых объектов в ANSI.

## <a name="when-not-to-use-pinvoke"></a>Когда не следует использовать PInvoke

Использование PInvoke не подходит для всех функций в стиле C в библиотеках DLL. Например, предположим, что в MyLib. dll имеется функция МакеспеЦиал, объявленная следующим образом:

`char * MakeSpecial(char * pszString);`

Если мы используем PInvoke в визуальном C++ приложении, мы можем написать нечто подобное следующему:

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

Сложность в том, что мы не можем удалить память для неуправляемой строки, возвращенной МакеспеЦиал. Другие функции, вызываемые через PInvoke, возвращают указатель на внутренний буфер, который не должен быть освобожден пользователем. В этом случае очевидным выбором является использование функции IJW.

## <a name="limitations-of-pinvoke"></a>Ограничения PInvoke

Невозможно возвратить тот же точный указатель из собственной функции, которая использовалась в качестве параметра. Если собственная функция возвращает указатель, который был упакован в него с помощью PInvoke, может возникнуть повреждение памяти и исключения.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

В следующем примере эта проблема возникает, и даже несмотря на то, что программа может дать правильный результат, выходные данные поступают из памяти, которая была освобождена.

```cpp
// platform_invocation_services_5.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
#include <limits.h>

ref struct MyPInvokeWrap {
public:
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]
   static String^ CharLower([In, Out] String ^);
};

int main() {
   String ^ strout = "AabCc";
   Console::WriteLine(strout);
   strout = MyPInvokeWrap::CharLower(strout);
   Console::WriteLine(strout);
}
```

## <a name="marshaling-arguments"></a>Аргументы упаковки

С `PInvoke`не требуется выполнять упаковку между управляемыми и C++ машинными примитивными типами с одной и той же формой. Например, не требуется выполнять упаковку между Int32 и int, а также между Double и Double.

Однако необходимо маршалировать типы, которые не имеют одной и той же формы. К ним относятся типы char, String и struct. В следующей таблице показаны сопоставления, используемые маршалером для различных типов:

|втипес. h|Visual C++|Визуальный C++ элемент с/CLR|Среда CLR|
|--------------|------------------|-----------------------------|-----------------------------|
|HANDLE|void \*|void \*|IntPtr, UIntPtr|
|BYTE|unsigned char|unsigned char|Byte|
|SHORT|short|short|Int16|
|WORD|unsigned short|unsigned short|UInt16|
|INT|int|int|Int32|
|UINT|unsigned int|unsigned int|UInt32|
|LONG|long|long|Int32|
|BOOL|long|bool|Логическое|
|DWORD|unsigned long|unsigned long|UInt32|
|ULONG|unsigned long|unsigned long|UInt32|
|CHAR|char|char|CHAR|
|LPCSTR|Char \*|Строка ^ [in], StringBuilder ^ [входные]|Строка ^ [in], StringBuilder ^ [входные]|
|LPCSTR|Константа char \*|Строка ^|String|
|LPWSTR|wchar_t \*|Строка ^ [in], StringBuilder ^ [входные]|Строка ^ [in], StringBuilder ^ [входные]|
|LPCWSTR|\* const wchar_t|Строка ^|String|
|FLOAT|FLOAT|FLOAT|Один|
|DOUBLE|double|double|С двойной точностью|

Модуль упаковки автоматически закрепляет память, выделенную в куче среды выполнения, если ее адрес передан неуправляемой функции. Закрепление предотвращает перемещение выделенного блока памяти в процессе сжатия сборщиком мусора.

В примере, приведенном ранее в этом разделе, параметр CharSet объекта DllImport указывает, как следует маршалировать управляемые строки. в этом случае они должны быть упакованы в строки ANSI для собственной стороны.

Сведения о упаковке для отдельных аргументов собственной функции можно указать с помощью атрибута MarshalAs. Существует несколько вариантов маршалирования строки \* аргумент: BStr, Ансибстр, Тбстр, LPStr, LPWStr и LPTStr. Значение по умолчанию — LPStr.

В этом примере строка маршалируется как строка двухбайтовых символов в Юникоде, LPWStr. Результатом является первая буква Hello World! так как второй байт упакованной строки имеет значение null, а помещает его в качестве маркера конца строки.

```cpp
// platform_invocation_services_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", EntryPoint="puts")]
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

Атрибут MarshalAs находится в пространстве имен System:: Runtime:: InteropServices. Атрибут может использоваться с другими типами данных, такими как массивы.

Как упоминалось ранее в разделе, Библиотека маршалирования предоставляет новый оптимизированный метод маршалирования данных между собственными и управляемыми средами. Дополнительные сведения см. в разделе Общие сведения о [маршалировании C++в ](../dotnet/overview-of-marshaling-in-cpp.md).

## <a name="performance-considerations"></a>Вопросы производительности

У PInvoke есть дополнительная нагрузка на вызов в диапазоне от 10 до 30 инструкций. Помимо этой фиксированной стоимости, маршалирование создает дополнительные издержки. Нет затрат на упаковку между преобразуемыми типами, которые имеют одинаковое представление в управляемом и неуправляемом коде. Например, нет никаких затрат на преобразование между int и Int32.

Для повышения производительности необходимо меньше вызовов PInvoke, которые маршалируются как можно больше данных, а не больше вызовов, которые маршалируются меньше данных на каждый вызов.

## <a name="see-also"></a>См. также:

[Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)
