---
title: Способы избегания исключений, создаваемых объектов COM, построенных с помощью - clr
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: 23af1d8b48a6579b8cc20261691c1f090dc858a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633445"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Способы избегания исключений во время завершения работы среды CLR при использовании COM-объектов, построенных с помощью /clr

После общеязыковой среды выполнения (CLR) переходит в режим завершения работы, собственных функций имеют ограниченный доступ к службам среды CLR. При попытке вызывать Release для COM-объект скомпилирован с **/CLR**, CLR в машинный код, а затем обратно в управляемый код для вызова функции IUnknown::Release (которая определяется в управляемом коде). Среда CLR не допускает вызов в управляемый код, так как она находится в режиме завершения работы.

Чтобы устранить эту проблему, убедитесь, что в деструкторах, вызываемых с помощью методов Release только содержит машинный код.

## <a name="see-also"></a>См. также

[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)