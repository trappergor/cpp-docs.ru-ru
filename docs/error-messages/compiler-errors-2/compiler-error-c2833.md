---
title: Ошибка компилятора C2833 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff066510292690bc940f18ab8d63605eb8627308
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2833"></a>Ошибка компилятора C2833
«оператор» не является распознаваемым оператором или типом  
  
 Слово `operator` должен следовать оператор, который вы хотите переопределить или тип, который нужно преобразовать.  
  
 Список операторов, которые можно определить в управляемом типе см. в разделе [определяемые пользователем операторы](../../dotnet/user-defined-operators-cpp-cli.md).  
  
 Следующий пример приводит к возникновению ошибки C2833:  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```