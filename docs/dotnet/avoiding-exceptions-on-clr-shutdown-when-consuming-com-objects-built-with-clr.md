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
ms.openlocfilehash: bafcfb4e8a8abfecc8491220202b63971bef1ac8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393835"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Способы избегания исключений во время завершения работы среды CLR при использовании COM-объектов, построенных с помощью /clr

После общеязыковой среды выполнения (CLR) переходит в режим завершения работы, собственных функций имеют ограниченный доступ к службам среды CLR. При попытке вызывать Release для COM-объект скомпилирован с **/CLR**, CLR в машинный код, а затем обратно в управляемый код для вызова функции IUnknown::Release (которая определяется в управляемом коде). Среда CLR не допускает вызов в управляемый код, так как она находится в режиме завершения работы.

Чтобы устранить эту проблему, убедитесь, что в деструкторах, вызываемых с помощью методов Release только содержит машинный код.

## <a name="see-also"></a>См. также

[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)
