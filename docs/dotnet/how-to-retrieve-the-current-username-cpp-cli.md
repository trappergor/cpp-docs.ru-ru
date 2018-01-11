---
title: "Как: извлечение текущего имени пользователя (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- current user names
- user names, retrieving
- UserName string
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1532647327c039994a1d09ee8b7eacc2c341f88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-retrieve-the-current-username-ccli"></a>Практическое руководство. Извлечение текущего имени пользователя (C++/CLI)
В следующем примере кода показано получение имени текущего пользователя (имя пользователя, выполнившего вход в Windows). Имя хранится в <xref:System.Environment.UserName%2A> строку, которая определена в <xref:System.Environment> пространства имен.  
  
## <a name="example"></a>Пример  
  
```  
// username.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операции Windows (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)