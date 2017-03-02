---
title: "Компилятор C4176 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4176
dev_langs:
- C++
helpviewer_keywords:
- C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
caps.latest.revision: 6
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
ms.openlocfilehash: ce8a7d1240e0f04265784c2c923c60f9136e5115
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4176"></a>Предупреждение компилятора (уровень 1) C4176
"подкомпонент": неизвестный компонент для директивы #pragma component browser  
  
 Директива pragma **component** содержит недопустимый подкомпонент. Чтобы исключить ссылки на определенное имя, необходимо использовать параметр **references** перед именем.  
  
## <a name="example"></a>Пример  
  
```  
// C4176.cpp  
// compile with: /W1 /LD  
#pragma component(browser, off, i)  // C4176  
#pragma component(browser, off, references, i) // ok  
```
