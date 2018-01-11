---
title: "Домены приложений и Visual C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a66731b9645458441f1c3e1f211c74be698e7231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="application-domains-and-visual-c"></a>Домены приложений и Visual C++
Если у вас есть `__clrcall` виртуальную функцию, в таблице vtable будет домена приложения (appdomain). При создании объекта в одном домене приложения, можно вызвать только виртуальную функцию в рамках этого домена приложения. Все функции, определенные в **/CLR: pure** использовать компилируемые объекты `__clrcall` соглашение о вызовах. Таким образом, все файлы vtable, определенные в **/CLR: pure** компилируемые объекты используются в appdomain. В смешанном режиме (**/CLR**) будет иметь каждого процесса файл vtable, если тип не имеет `__clrcall` виртуальные функции. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Дополнительные сведения см. в разделе .  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [Как: переход на/CLR: pure (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)