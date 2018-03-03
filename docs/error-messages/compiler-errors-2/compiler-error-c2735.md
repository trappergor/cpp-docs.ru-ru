---
title: "Ошибка компилятора C2735 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2735
dev_langs:
- C++
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d89ee76a526ca1ea41993153f5065c5270c2830
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2735"></a>Ошибка компилятора C2735
Ключевое слово «ключевое слово» является недопустимым в спецификаторе типа формального параметра  
  
 Ключевое слово не допускается в данном контексте.  
  
 Следующий пример приводит к возникновению ошибки C2735:  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```