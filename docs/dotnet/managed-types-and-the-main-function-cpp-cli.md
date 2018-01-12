---
title: "Управляемые типы и функция main (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- main function, in managed applications
- managed code, main() function
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 706cd8b15dffb1cde4fc5bbc399789b2aafd6ddf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="managed-types-and-the-main-function-ccli"></a>Управляемые типы и функция main (C++/CLI)
При написании приложения с использованием **/CLR**, аргументы **main()** функция не может иметь управляемый тип.  
  
 Пример правильной подписи выглядит:  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## <a name="see-also"></a>См. также  
 [Управляемые типы (C++/CLI)](../dotnet/managed-types-cpp-cli.md)