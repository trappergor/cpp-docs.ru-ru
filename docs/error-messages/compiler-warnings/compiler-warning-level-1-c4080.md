---
title: "Компилятор C4080 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4080
dev_langs:
- C++
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b6925342af8863ce0459ff940282c921999b2d86
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4080"></a>Предупреждение компилятора (уровень 1) C4080
Требуется идентификатор для имени сегмента; имеется "символ"  
  
 Имя сегмента в [#pragma alloc_text](../../preprocessor/alloc-text.md) должен быть строкой или идентификатором. Компилятор игнорирует директиву pragma, если не удается найти допустимый идентификатор.  
  
 При компиляции следующего примера будет выдано предупреждение C4080:  
  
```  
// C4080.cpp  
// compile with: /W1  
extern "C" void func(void);  
  
#pragma alloc_text()   // C4080  
  
// try this line to resolve the warning  
// #pragma alloc_text("mysection", func)  
  
int main() {  
}  
  
void func(void) {  
}  
```
