---
title: Способы избегания исключений, создаваемых объектов COM, построенных с помощью - clr | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 687585d0b25c64f5575646de3cd4823e0a89988e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408990"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Способы избегания исключений во время завершения работы среды CLR при использовании COM-объектов, построенных с помощью /clr

После общеязыковой среды выполнения (CLR) переходит в режим завершения работы, собственных функций имеют ограниченный доступ к службам среды CLR. При попытке вызывать Release для COM-объект скомпилирован с **/CLR**, CLR в машинный код, а затем обратно в управляемый код для вызова функции IUnknown::Release (которая определяется в управляемом коде). Среда CLR не допускает вызов в управляемый код, так как она находится в режиме завершения работы.

Чтобы устранить эту проблему, убедитесь, что в деструкторах, вызываемых с помощью методов Release только содержит машинный код.

## <a name="see-also"></a>См. также

[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)