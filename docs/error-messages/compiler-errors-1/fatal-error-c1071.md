---
title: "Неустранимая ошибка C1071 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1071
dev_langs: C++
helpviewer_keywords: C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: acd48401d3abc17d994e861bf6fb046450d88ca6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1071"></a>Неустранимая ошибка C1071
непредвиденное обнаружение конца файла в комментарии  
  
 Компилятор достигнут конец файла при просмотре комментария.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Отсутствует признак конца комментария (* /).  
  
2.  Отсутствует символ перевода строки после комментария в последней строке исходного файла.  
  
 Следующий пример приводит к возникновению ошибки C1071:  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```