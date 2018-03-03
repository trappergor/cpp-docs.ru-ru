---
title: "Предупреждение (уровень 3) C4995 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4995
dev_langs:
- C++
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c8bf04670f8899209a42e2cc8d20420d522ef4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4995"></a>Компилятор предупреждение (уровень 3) C4995
«функция»: имя помечено как #pragma deprecated  
  
 Компилятор обнаружил функцию, которая была помечена с помощью директивы pragma [устаревшими](../../preprocessor/deprecated-c-cpp.md). Функция может не поддерживаться в будущих выпусках. Вы можно отключить это предупреждение с [предупреждение](../../preprocessor/warning.md) pragma (пример ниже).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4995:  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```