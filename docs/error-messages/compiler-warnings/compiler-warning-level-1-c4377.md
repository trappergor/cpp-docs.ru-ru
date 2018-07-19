---
title: Предупреждение (уровень 1) C4377 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef049f85cd17bfeaba243b84da9fca93ae4036b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274785"
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