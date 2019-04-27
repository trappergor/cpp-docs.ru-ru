---
title: Домены приложений и Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 2296654e6935bc40f301226b184cf34f77cb126d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223037"
---
# <a name="application-domains-and-visual-c"></a>Домены приложений и Visual C++

Если у вас есть `__clrcall` виртуальную функцию, в таблице vtable будет домена приложения (appdomain). При создании объекта в одном домене приложения, может вызывать только виртуальную функцию в рамках этого домена приложения. В смешанном режиме (**/CLR**) вы получите файл vtable каждого процесса, если ваш тип не содержит `__clrcall` виртуальные функции. **/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

Дополнительные сведения:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>См. также

- [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)