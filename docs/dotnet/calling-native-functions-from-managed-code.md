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
ms.openlocfilehash: 0cdd5db4fae8d9167fa9ab1aeb6a4e8cbfe76ded
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372512"
---
# <a name="calling-native-functions-from-managed-code"></a>Вызов неуправляемых функций из управляемого кода

Общее время выполнения языка предоставляет службы вызова платформы, или PInvoke, что позволяет управляемому коду вызывать функции C-стиля в родных динамических библиотеках (DLL). Для ком-совместимости с временем выполнения и для механизма "It Just Works" или IJW используется тот же объем маршалинга данных.

Дополнительные сведения см. в разделе:

- [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

Образцы в этом разделе `PInvoke` просто иллюстрируют, как можно использовать. `PInvoke`может упростить настраиваемый маршалинг данных, поскольку вы предоставляете информацию о маршализации декларативно в атрибутах вместо того, чтобы писать процедурный код маршалинга.

> [!NOTE]
> Библиотека маршалов предоставляет альтернативный способ оптимизации данных между родной и управляемой средами. Дополнительную информацию о библиотеке маршалинга можно [освяить](../dotnet/overview-of-marshaling-in-cpp.md) в см. Библиотека маршалов может быть пригодна только для данных, а не для функций.

## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke и атрибут DllImport

Ниже приводится пример `PInvoke` использования программы Visual C'. Родная функция ставит определяется в msvcrt.dll. Атрибут DllImport используется для декларирования ставит.

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

Следующая выборка эквивалентна предыдущей выборке, но использует IJW.

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

- Нет необходимости писать `DLLImport` объявления атрибутов для неуправляемых AIS, которые использует программа. Просто включите файл заголовка и ссылку с библиотекой импорта.

- Механизм IJW немного быстрее (например, заглушки IJW не нужно проверять на необходимость прикрепить или скопировать элементы данных, потому что это делается явно разработчиком).

- Он четко иллюстрирует проблемы производительности. В этом случае тот факт, что вы переводите со строки Unicode на строку ANSI и что у вас есть сопутствующие распределения памяти и распределения. В этом случае разработчик, пишущий код с помощью IJW, поймет, что вызов `_putws` и использование `PtrToStringChars` будут лучше для производительности.

- Если вы называете много неуправляемых AIS, используя одни и те же данные, то их один раз и передача маршализированной копии гораздо эффективнее, чем каждый раз переквалификация.

### <a name="disadvantages-of-ijw"></a>Недостатки IJW

- Маршалинг должен быть четко указан в коде, а не атрибутами (которые часто имеют соответствующие значения по умолчанию).

- Код маршалинга является внеочередным, где он является более инвазивным в потоке логики приложения.

- Поскольку явные марширование AIS возвращает `IntPtr` типы для 32-битной `ToPointer` переносимости, необходимо использовать дополнительные вызовы.

Конкретный метод, выставленный с помощью СЗ, является более эффективным, явным методом, за счет некоторой дополнительной сложности.

Если приложение использует в основном неуправляемые типы данных или если оно вызывает больше неуправляемых AI, чем AI.NET Framework, мы рекомендуем использовать функцию IJW. Чтобы вызвать случайный неуправляемый API в основном управляемом приложении, выбор более тонкий.

## <a name="pinvoke-with-windows-apis"></a>PInvoke с AIS для Windows

PInvoke удобен для вызова функций в Windows.

В этом примере программа Visual C' взаимодействует с функцией MessageBox, которая является частью API Win32.

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

Выход представляет собой поле сообщений, которое имеет название PInvoke Test и содержит текст Hello World!.

Информация о маршалах также используется PInvoke для поиска функций в DLL. В user32.dll на самом деле нет функции MessageBox, но CharSet-CharSet::Ansi позволяет PInvoke использовать MessageBoxA, версию ANSI, вместо MessageBoxW, которая является версией Unicode. Как правило, мы рекомендуем использовать версии неуправляемых AI Unicode, поскольку это исключает накладные расходы на перевод из родного формата Unicode объектов строки .NET Framework в ANSI.

## <a name="when-not-to-use-pinvoke"></a>Когда не использовать PInvoke

Использование PInvoke не подходит для всех функций C-стиля в DLL. Например, предположим, что есть функция MakeSpecial в mylib.dll, объявленная следующим образом:

`char * MakeSpecial(char * pszString);`

Если мы используем PInvoke в приложении Visual C, мы можем написать что-то похожее на следующее:

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

Сложность здесь заключается в том, что мы не можем удалить память для неуправляемой строки, возвращенной MakeSpecial. Другие функции, вызванные через PInvoke, возвращают указатель во внутренний буфер, который не должен быть разослан пользователем. В этом случае использование функции IJW является очевидным выбором.

## <a name="limitations-of-pinvoke"></a>Ограничения PInvoke

Вы не можете вернуть тот же точный указатель из родной функции, который вы взяли в качестве параметра. Если родная функция возвращает указатель, который был примкнул к ней PInvoke, может возникнуть порча памяти и исключения.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

Следующий образец демонстрирует эту проблему, и даже если программа может показаться, чтобы дать правильный выход, выход идет из памяти, которые были освобождены.

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

## <a name="marshaling-arguments"></a>Аргументы маршалинга

С `PInvoke`, не marshaling не требуется между управляемым и СЗ родной примитивных типов с той же формой. Например, между Int32 и Int, или между Double и Double, не требуется маршалинг.

Тем не менее, необходимо иметь типы маршалов, которые не имеют той же формы. Это включает в себя типы char, string и struct. В следующей таблице показаны отображения, используемые маршалом для различных типов:

|wtypes.h|Visual C++|Визуальный КЗ с /clr|Среда CLR|
|--------------|------------------|-----------------------------|-----------------------------|
|HANDLE|Void\*|Void\*|IntPtr, UIntPtr|
|BYTE|unsigned char|unsigned char|Byte|
|SHORT|short|short|Int16|
|WORD|unsigned short|unsigned short|UInt16|
|INT|INT|INT|Int32|
|UINT|unsigned int|unsigned int|UInt32|
|LONG|long|long|Int32|
|BOOL|long|bool|Логическое|
|DWORD|unsigned long|unsigned long|UInt32|
|ULONG|unsigned long|unsigned long|UInt32|
|CHAR|char|char|CHAR|
|LPSTR|Char\*|Струнная строка , StringBuilder , (в, вне)|Струнная строка , StringBuilder , (в, вне)|
|LPCSTR|const char \*|Строка|Строка|
|LPWSTR|Wchar_t\*|Струнная строка , StringBuilder , (в, вне)|Струнная строка , StringBuilder , (в, вне)|
|LPCWSTR|const wchar_t \*|Строка|Строка|
|FLOAT|FLOAT|FLOAT|Один|
|DOUBLE|double|double|Double|

Marshaler автоматически прикрепляет память, выделенную на куче времени выполнения, если ее адрес передается неуправляемой функции. Закрепление предотвращает перемещение сборщика мусора выделенного блока памяти во время уплотнения.

В примере, показанном ранее в этой теме, параметр CharSet DllImport определяет, как должны быть маршализированы управляемые строки; в этом случае они должны быть пристечены к строкам ANSI для родной стороны.

Вы можете указать информацию о маршализации для отдельных аргументов родной функции с помощью атрибута MarshalAs. Существует несколько вариантов для \* аргумента строки: BStr, ANSIBStr, TBStr, LPStr, LPWStr и LPTStr. По умолчанию является LPStr.

В этом примере строка используется в виде двухбайной строки символов Unicode, LPWStr. Выход является первой буквой Hello World! потому что второй байт маршализированной строки является нулевым, и ставит интерпретирует это как маркер конца строки.

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

Атрибут MarshalAs находится в системе::Runtime::InteropServices namespace. Атрибут может быть использован с другими типами данных, такими как массивы.

Как упоминалось ранее в теме, библиотека маршалинга предоставляет новый, оптимизированный метод обработки данных между родной и управляемой средой. Для получения дополнительной [информации, см.](../dotnet/overview-of-marshaling-in-cpp.md)

## <a name="performance-considerations"></a>Особенности производительности

PInvoke имеет накладные расходы между 10 и 30 x86 инструкций за звонок. В дополнение к этой фиксированной стоимости, маршалинг создает дополнительные накладные расходы. Не существует затрат на переплату между типами blittable, которые имеют одинаковое представление в управляемом и неуправляемом коде. Например, перевод между Int и Int32 не обходится.

Для повышения производительности, иметь меньше PInvoke звонки, что маршал столько данных, сколько возможно, вместо того, чтобы больше звонков, что маршал меньше данных за вызов.

## <a name="see-also"></a>См. также раздел

[Взаимосвязь между коренными жителями и .NET](../dotnet/native-and-dotnet-interoperability.md)
