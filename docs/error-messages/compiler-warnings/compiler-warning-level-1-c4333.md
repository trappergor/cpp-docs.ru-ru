---
title: Предупреждение (уровень 1) C4333 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4333
dev_langs:
- C++
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67fb838ecbf34f1fb09242a93f6943d81fd0de1e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282470"
---
# <a name="compiler-warning-level-1-c4333"></a>Предупреждение компилятора (уровень 1) C4333
«оператор»: сдвиг вправо слишком большое значение, потери данных  
  
 Операция сдвига вправо была слишком большой процент.  Все значимые биты сдвинуты без и результат всегда будет равно нулю.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4333.  
  
```  
// C4333.cpp  
// compile with: /c /W1  
unsigned shift8 (unsigned char c) {  
   return c >> 8;   // C4333  
  
   // try the following line instead  
   // return c >> 4;   // OK  
}  
```