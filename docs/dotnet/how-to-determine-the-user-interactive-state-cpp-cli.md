---
title: "Как: определение интерактивного состояния пользователя (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, user interactive state
- user interactive state
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f65933a1cbd81c0794263dfe3fa2628f52599257
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-determine-the-user-interactive-state-ccli"></a>Практическое руководство. Определение интерактивного состояния пользователя (C++/CLI)
В следующем примере кода показано, как определить, выполняется ли код в контексте, взаимодействия с пользователем. Если <xref:System.Environment.UserInteractive%2A> имеет значение false, то код выполняется как процесс службы или из веб-приложения, в этом случае вам не следует пытаться взаимодействовать с пользователем.  
  
## <a name="example"></a>Пример  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операции Windows (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)