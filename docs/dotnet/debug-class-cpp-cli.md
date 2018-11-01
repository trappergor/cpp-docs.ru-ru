---
title: Класс Debug (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
ms.openlocfilehash: ae400783112ca44a75f1224a9e8d6ebe52414070
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662479"
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