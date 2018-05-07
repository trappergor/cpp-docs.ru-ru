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
ms.openlocfilehash: 8ddb60b3fad6c230677e2098dd89a723198bea8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="application-domains-and-visual-c"></a>Домены приложений и Visual C++
Если у вас есть `__clrcall` виртуальную функцию, в таблице vtable будет домена приложения (appdomain). При создании объекта в одном домене приложения, можно вызвать только виртуальную функцию в рамках этого домена приложения. В смешанном режиме (**/CLR**) будет иметь каждого процесса файл vtable, если тип не имеет `__clrcall` виртуальные функции. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Дополнительные сведения см. в разделе .  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)