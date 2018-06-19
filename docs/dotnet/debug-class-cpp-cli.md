---
title: Класс Debug (C + +/ CLI) | Документы Microsoft
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
ms.openlocfilehash: fddf192b21b878c82ca663da657c55e32fd9173d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106210"
---
# <a name="debug-class-ccli"></a>Класс Debug (C++/CLI)
При использовании <xref:System.Diagnostics.Debug> в приложении Visual C++ поведение не меняется между отладки и выпуска.  
  
## <a name="remarks"></a>Примечания  
 Поведение для <xref:System.Diagnostics.Trace> идентично поведению для класса Debug, однако зависит от определяемого символа TRACE. Это означает, что следует `#ifdef` любой код, связанные с трассировкой для отключения поведения отладки в сборке выпуска.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере выполняются всегда выходные данные инструкции, независимо от того, является ли компилировать с **/DDEBUG** или **/DTRACE**.  
  
### <a name="code"></a>Код  
  
```  
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
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Для получения ожидаемого поведения (то есть выходные данные «test» выдает для сборки выпуска), необходимо использовать `#ifdef` и `#endif` директивы. В предыдущем примере кода изменяется ниже приведен:  
  
### <a name="code"></a>Код  
  
```  
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