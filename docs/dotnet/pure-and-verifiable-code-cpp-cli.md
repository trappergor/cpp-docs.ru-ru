---
title: Чистый и проверяемый код (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 453bb40e94c1d345adbe22f8792b59d1e584499a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704832"
---
# <a name="pure-and-verifiable-code-ccli"></a>Чистый и проверяемый код (C + +/ CLI)

Для программирования .NET, Visual C++ в Visual Studio 2017 г. поддерживает создание смешанных сборок с помощью [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора. **/CLR: pure** и **CLR: safe** параметры являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г. Если код должен быть безопасным или проверки, затем рекомендуется переносить его в C#.

## <a name="mixed-clr"></a>Смешанный (/ clr)

Смешанные сборки (скомпилированные с **/CLR**), содержат как неуправляемые и управляемые части, что позволяет им использовать функции .NET, но по-прежнему содержать машинный код. Это позволяет приложениям и компонентам обновляться для использования функций .NET без необходимости переписать всего проекта. С помощью Visual C++ управляемый и машинный код таким образом, называется взаимодействия C++. Дополнительные сведения см. в разделе [сборки смешанный (машинный и управляемый код)](../dotnet/mixed-native-and-managed-assemblies.md) и [машинного кода и .NET-взаимодействии](../dotnet/native-and-dotnet-interoperability.md).

Вызовы, выполненные из управляемых сборок в собственные библиотеки DLL с помощью вызова P/Invoke будет скомпилирован, но может завершиться ошибкой во время выполнения в зависимости от параметров безопасности.

Имеется один сценарий кодирования, будет пропущен компилятором, но приведет сборку непроверяемый: вызов виртуальной функции через экземпляр объекта с помощью оператора разрешения области действия.  Например, `MyObj -> A::VirtualFunction();`.

## <a name="see-also"></a>См. также

- [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

