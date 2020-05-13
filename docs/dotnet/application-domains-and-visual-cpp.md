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
ms.openlocfilehash: 16c02bb58681ecb241d3552f57e0b05f2d6711b4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208810"
---
# <a name="application-domains-and-visual-c"></a>Домены приложений и Visual C++

Если у вас есть виртуальная функция `__clrcall`, то таблица vtable будет использоваться для каждого домена приложений (AppDomain). При создании объекта в одном AppDomain можно вызвать только виртуальную функцию из этого AppDomain. В смешанном режиме ( **/CLR**) у вас будут виртуальные таблицы vtable для каждого процесса, если у типа нет `__clrcall` виртуальных функций. Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

Дополнительные сведения см. в разделе:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>См. также раздел

- [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)
