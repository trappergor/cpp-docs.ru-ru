---
title: Класс Debug (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
ms.openlocfilehash: 3a262a0d2ef429cb94f4648eb7c7180e7b130279
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393783"
---
# <a name="debug-class-ccli"></a>Класс Debug (C++/CLI)

При использовании <xref:System.Diagnostics.Debug> в приложении Visual C++, поведение не меняется между отладки и выпуска.

## <a name="remarks"></a>Примечания

Поведение для <xref:System.Diagnostics.Trace> идентично поведению для класса Debug, но зависит от определяемого символа TRACE. Это означает, что вы должны `#ifdef` любой код, связанные с трассировкой для отключения поведения отладки в окончательной сборке.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Следующий пример всегда выполняет инструкции выходные данные, независимо от того, является ли компиляции с параметром **/DDEBUG** или **/DTRACE**.

### <a name="code"></a>Код

```cpp
// mcpp_debug_class.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
   Trace::Unindent();

   Debug::WriteLine("test");
}
```

### <a name="output"></a>Вывод

```Output
    Entering Main
Hello World.
    Exiting Main
test
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Чтобы получить ожидаемое поведение (то есть выходные данные «test» в удобном для сборки выпуска), необходимо использовать `#ifdef` и `#endif` директивы. В предыдущем примере кода изменяется ниже приведен:

### <a name="code"></a>Код

```cpp
// mcpp_debug_class2.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();

#ifdef TRACE   // checks for a debug build
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
#endif
   Trace::Unindent();

#ifdef DEBUG   // checks for a debug build
   Debug::WriteLine("test");
#endif   //ends the conditional block
}
```

## <a name="see-also"></a>См. также

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
