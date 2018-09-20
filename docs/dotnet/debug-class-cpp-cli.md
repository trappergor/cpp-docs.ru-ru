---
title: Класс Debug (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: eecda10f2fd88b902a54fe9f4dc4de8edc4bc1b0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413566"
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