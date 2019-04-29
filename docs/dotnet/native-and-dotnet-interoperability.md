---
title: Взаимодействие исходного кода и платформы.NET
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++]
- .NET Framework [C++], interoperability with Visual C++
- interoperability [C++], about .NET interoperability
- interop [C++], about .NET interoperability
- managed code [C++], interoperability
- native code [C++]
- interoperability [C++]
- MFC [C++], .NET integration
- unmanaged code interoperability [C++]
- Visual C++, interoperability
- native code [C++], .NET interoperatibility
ms.assetid: f3ec6c99-c745-4256-b95b-f1d12ba17a5a
ms.openlocfilehash: 486796e404ad1aee39fbeb85251d26cc078b1160
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384794"
---
# <a name="native-and-net-interoperability"></a>Взаимодействие исходного кода и платформы.NET

Visual C++ поддерживает возможности взаимодействия, позволяющие управляемых и неуправляемых конструкций, сосуществовать и взаимодействовать в той же сборке и даже в том же файле. Небольшое подмножество этой функции, такие как P/Invoke, поддерживается в других языках .NET, но большая часть поддержки взаимодействия, предоставляемой Visual C++ не поддерживается на других языках.

## <a name="in-this-section"></a>В этом разделе

[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
Описание сборок, созданных с помощью [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) параметра компилятора, который одновременно содержать управляемые и неуправляемые функции.

[Использование пользовательского элемента управления формы Windows Forms в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
В этой статье описывается использование вспомогательных классов MFC Windows Forms для размещения элементов управления Windows Forms в приложениях MFC.

[Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)<br/>
Описывает, как библиотеки DLL, не к CLR может использоваться в приложениях .NET.
