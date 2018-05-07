---
title: Предупреждение (уровень 1) C4087 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4087
dev_langs:
- C++
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5b9962abc29b94425f96c978f3dd7e8d3f7c251
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4087"></a>Предупреждение компилятора (уровень 1) C4087
"функция": объявлена со списком параметров void  
  
 Объявление функции не имеет формальных параметров, но вызов функции содержит фактические параметры. Лишние параметры передаются в соответствии с соглашением о вызовах функции.  
  
 Это предупреждение для компилятора C.  
  
## <a name="example"></a>Пример  
  
```  
// C4087.c  
// compile with: /W1  
int f1( void ) {  
}  
  
int main() {  
   f1( 10 );   // C4087  
}  
```