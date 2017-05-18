---
title: "Ошибка компилятора C2833 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2fbe6bcb1850948d4484fca93f2cd511a9e2a1da
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2833"></a>Ошибка компилятора C2833
«оператор» не является распознаваемым оператором или типом  
  
 Слово `operator` должен следовать оператор, который требуется переопределить или типа, который необходимо преобразовать.  
  
 Список операторов, которые можно определить в управляемом типе см. в разделе [определяемые пользователем операторы](../../dotnet/user-defined-operators-cpp-cli.md).  
  
 Следующий пример приводит к возникновению ошибки C2833:  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```
