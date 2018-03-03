---
title: "Как: определить руководство (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d89fa475c997e0842ef9de5a21c26e664f25d78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-determine-if-shutdown-has-started-ccli"></a>Практическое руководство. Определение начала процесса завершения работы (C++/CLI)
В следующем примере кода показано, как определить, завершается ли в данный момент приложение или .NET Framework. Он полезен при доступе к статическим элементам в платформе .NET Framework, поскольку во время завершения работы, эти конструкции завершается системой и не могут использоваться. Проверив <xref:System.Environment.HasShutdownStarted%2A> свойства во-первых, можно избежать потенциальных сбоев не доступ к этим элементам.  
  
## <a name="example"></a>Пример  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операции Windows (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)