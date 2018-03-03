---
title: "Ошибка средств компоновщика LNK2028 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7441dcd893e3e814d738f228d002a947e7f43c8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2028"></a>Ошибка средств компоновщика LNK2028
«exported_function» (decorated_name) на которые ссылается функция «function_containing_function_call» (decorated_name)  
  
 При попытке импортировать собственную функцию в чистом образе, следует помнить, что неявные соглашения о вызовах различаются внутренней и чистой компиляции.  
  
## <a name="example"></a>Пример  
 Этот пример кода приводит к возникновению ошибки компонента с экспортированного native, функции которого соглашение о вызовах является неявно [__cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере создается чистый клиент, использующий внутреннюю функцию. Тем не менее соглашение о вызовах в **/CLR: pure** — [__clrcall](../../cpp/clrcall.md). Следующий пример приводит к возникновению ошибки LNK2028.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```