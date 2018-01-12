---
title: "Предупреждение (уровень 1) C4319 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4319
dev_langs: C++
helpviewer_keywords: C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7008b0f618048f5a4538a7aff55f03bab3d406d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4319"></a>Предупреждение компилятора (уровень 1) C4319
operator: нулевое расширение type в type большего размера  
  
 Результат оператора ~ (побитовое дополнение) не имеет знака и затем использует нулевое расширение при преобразовании к большему типу.  
  
 В следующем примере ~(a - 1) вычисляется как 32-разрядное выражение long без знака и затем преобразуется в 64-разрядное с помощью нулевого расширения. Это может привести к непредвиденному результату операции.  
  
```  
// C4319.cpp  
// compile with: cl /W4 C4319.cpp  
int main() {  
   unsigned long a = 0;  
   unsigned long long q = 42;  
   q = q & ~(a - 1);    // C4319 expected  
}  
```