---
title: Ошибка средств компоновщика LNK2028 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7347e8edda7ad8b317d4e6e02dfc9345ac76f269
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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