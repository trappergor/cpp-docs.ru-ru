---
title: "Предотвращение исключений, вызванных объектов COM, построенных с - clr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 287c9831f8c604272b37ac85528d66fe640de557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Способы избегания исключений во время завершения работы среды CLR при использовании COM-объектов, построенных с помощью /clr
После общеязыковой среды выполнения (CLR) переходит в режим завершения работы, собственных функций имеют ограниченный доступ к службам среды CLR. При попытке вызывать Release для COM-объекта компиляции с **/CLR**, среда CLR в машинный код, а затем обратно в управляемый код для вызова функции IUnknown::Release (которая определена в управляемом коде). Среда CLR предотвращает вызов в управляемом коде, поскольку она находится в режиме завершения работы.  
  
 Для решения этой проблемы убедитесь, что деструктор, вызываемый с помощью методов Release содержит только машинный код.  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)