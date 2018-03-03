---
title: "Предупреждение (уровень 4) C4565 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b89da26312c68bc76d23fc829a14f17db3d601b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4565"></a>Предупреждение компилятора (уровень 4) C4565
«функция»: переопределение; символ был объявлен ранее при помощи __declspec(модификатор)  
  
 Символ был или определении и второе определение или объявление, в отличие от первого определения или объявления, не имели `__declspec` модификатор (***модификатор***). Это предупреждение носит информационный характер. Чтобы устранить это предупреждение, удалите одно из определений.  
  
 Следующий пример приводит к возникновению ошибки C4565:  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```