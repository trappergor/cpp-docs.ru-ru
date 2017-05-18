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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 70b0311ff02fc9c5fb2b06005a639d0a3dca21e4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4565"></a>Предупреждение компилятора (уровень 4) C4565
«функция»: переопределение; символ был объявлен ранее при помощи __declspec(модификатор)  
  
 Символ был или определении и второй определения или объявления, в отличие от первого определения или объявления, не имеет `__declspec` модификатор (***модификатор***). Это предупреждение носит информационный характер. Чтобы устранить это предупреждение, удалите одно из определений.  
  
 Следующий пример приводит к возникновению ошибки C4565:  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```
