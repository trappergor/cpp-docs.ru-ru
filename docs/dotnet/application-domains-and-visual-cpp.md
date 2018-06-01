---
title: Домены приложений и Visual C++ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b935b9a5d1561fa1c8b961ee48b92f59b98e2bd2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704338"
---
# <a name="application-domains-and-visual-c"></a>Домены приложений и Visual C++

Если у вас есть `__clrcall` виртуальную функцию, в таблице vtable будет домена приложения (appdomain). При создании объекта в одном домене приложения, можно вызвать только виртуальную функцию в рамках этого домена приложения. В смешанном режиме (**/CLR**) будет иметь файл vtable каждого процесса, если тип не имеет `__clrcall` виртуальные функции. **/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

Дополнительные сведения:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>См. также

- [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)