---
title: Предотвращение исключений, вызванных объектов COM, построенных с - clr | Документы Microsoft
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
ms.openlocfilehash: 0efd2af7eb4bf8a70bff983d627f802f1976c6ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Способы избегания исключений во время завершения работы среды CLR при использовании COM-объектов, построенных с помощью /clr
После общеязыковой среды выполнения (CLR) переходит в режим завершения работы, собственных функций имеют ограниченный доступ к службам среды CLR. При попытке вызывать Release для COM-объекта компиляции с **/CLR**, среда CLR в машинный код, а затем обратно в управляемый код для вызова функции IUnknown::Release (которая определена в управляемом коде). Среда CLR предотвращает вызов в управляемом коде, поскольку она находится в режиме завершения работы.  
  
 Для решения этой проблемы убедитесь, что деструктор, вызываемый с помощью методов Release содержит только машинный код.  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)