---
title: "Предупреждение компилятора (уровень 3) C4995 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4995"
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": имя было помечено прагма\-директивой \#pragma deprecated  
  
 Компилятор обнаружил функцию, помеченную прагма\-директивой [deprecated](../Topic/deprecated%20\(C-C++\).md).  Функция может не поддерживаться в будущих выпусках.  Это предупреждение можно отключить с помощью прагма\-директивы [warning](../../preprocessor/warning.md) \(см. пример ниже\).  
  
## Пример  
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