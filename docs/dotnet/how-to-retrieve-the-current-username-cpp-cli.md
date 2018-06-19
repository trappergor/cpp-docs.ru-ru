---
title: 'Как: извлечение текущего имени пользователя (C + +/ CLI) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current user names
- user names, retrieving
- UserName string
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48b48b2d6ad84a85ca100c45a87f5d5037de684f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127826"
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