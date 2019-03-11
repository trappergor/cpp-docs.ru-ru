---
title: Чистый и проверяемый код (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
ms.openlocfilehash: 66f3b5a33791d20297cde6e6223ba65189a99682
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743840"
---
# <a name="pure-and-verifiable-code-ccli"></a>Чистый и проверяемый код (C + +/ CLI)

Для программирования .NET, Visual C++ в Visual Studio 2017 поддерживает создание смешанных сборок с помощью [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора. **/CLR: pure** и **CLR: safe** параметры признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017. Если ваш код должен быть безопасным или проверяемых, то мы рекомендуем портировать его с C#.

## <a name="mixed-clr"></a>Смешанный (/ clr)

Смешанные сборки (скомпилированные с использованием **/CLR**), содержат как неуправляемые и управляемые части, что позволяет им использовать компоненты .NET, но по-прежнему содержать машинный код. Это позволяет приложениям и компонентам обновляться для использования функций .NET без необходимости переписать весь проект. С помощью Visual C++, чтобы смешивать управляемый и машинный код таким образом, называется взаимодействия C++. Дополнительные сведения см. в разделе [смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md) и [машинный код и платформы.NET](../dotnet/native-and-dotnet-interoperability.md).

Вызовы из управляемых сборок в собственные библиотеки DLL с помощью P/Invoke будет скомпилирован, но может завершиться ошибкой во время выполнения в зависимости от параметров безопасности.

Имеется один сценарий кодирования, будет пропущен компилятором, но это приведет к непроверяемый сборки: вызов виртуальной функции через экземпляр объекта, с помощью оператора разрешения области действия.  Например, `MyObj -> A::VirtualFunction();`.

## <a name="see-also"></a>См. также

- [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
