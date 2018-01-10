---
title: "Предупреждение (уровень 1) C4377 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4377
dev_langs: C++
helpviewer_keywords: C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b2cf61aa35bcfc40a40febb9e066caba6decd682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4377"></a>Предупреждение компилятора (уровень 1) C4377
собственные типы являются закрытыми по умолчанию; -d1PrivateNativeTypes запрещен  
  
 В предыдущих выпусках собственные типы в сборках были открытыми по умолчанию, а параметр компилятора внутренней, недокументированной (**/d1PrivateNativeTypes**) был использован для их преобразования в закрытый.  
  
 Все типы в собственном и среда CLR, теперь являются закрытыми по умолчанию в сборке, поэтому **/d1PrivateNativeTypes** больше не нужен.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4377.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```