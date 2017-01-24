---
title: "Предупреждение компилятора (уровень 1) C4556 | Microsoft Docs"
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
  - "xml"
  - "C4556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4556"
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Значение встроенного аргумента интерпретации "значение" лежит вне диапазона "нижняя граница — верхняя граница"  
  
 Встроенный аргумент совпадает с аппаратной инструкцией.  В аппаратной инструкции константа кодируется с помощью фиксированного количества битов.  Если ***значение*** лежит за пределами диапазона, оно будет закодировано с ошибкой.  Лишние биты будут отсечены компилятором.  
  
 Следующий пример приводит к возникновению ошибки C4556:  
  
```  
// C4556.cpp  
// compile with: /W1  
// processor: x86 IPF  
#include <xmmintrin.h>  
void test()  
{  
   __m64 m;  
   _m_pextrw(m, 5);   // C4556  
}  
int main()  
{  
}  
```