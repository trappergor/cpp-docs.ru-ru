---
title: "Предупреждение (уровень 1) C4160 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4160
dev_langs:
- C++
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: e8662a40b81a18ab4eed2fe50467977879762371
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4160"></a>Предупреждение компилятора (уровень 1) C4160
**#pragma**   
 ***Директива pragma* (pop,...): не найден ранее занесенный в стек идентификатор "**   
 ***Идентификатор* "**  
  
 Оператор pragma в исходном коде пытается извлечь из стека идентификатор, который не был занесен в стек. Чтобы устранить это предупреждение, необходимо убедиться в том, что идентификатор, извлекаемый из стека, был туда соответствующим образом занесен.  
  
 Следующий пример приводит к возникновению предупреждения C4160:  
  
```  
// C4160.cpp  
// compile with: /W1  
#pragma pack(push)  
  
#pragma pack(pop, id)   // C4160  
// use identifier when pushing to resolve the warning  
// #pragma pack(push, id)  
  
int main() {  
}  
```
