---
title: 'Как: извлечение имени локального компьютера (C + +/ CLI) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- computer name, retrieving
- machine name, retrieving
- computer name
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f02c9d12809ef908415c58c6b04da2597a3a1bfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128645"
---
# <a name="how-to-retrieve-the-local-machine-name-ccli"></a>Практическое руководство. Извлечение имени локального компьютера (C++/CLI)
В следующем примере кода демонстрируется извлечение имени локального компьютера (имя компьютера, которое отображается в сети). Это можно сделать путем получения <xref:System.Environment.MachineName%2A> строку, которая определена в <xref:System.Environment> пространства имен.  
  
## <a name="example"></a>Пример  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операции Windows (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)