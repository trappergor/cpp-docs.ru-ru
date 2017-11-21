---
title: "Ошибка компилятора C2874 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2874
dev_langs: C++
helpviewer_keywords: C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b5567e796dca8161491e0764523140b516bce886
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2874"></a>Ошибка компилятора C2874
с помощью объявление вызвало наличие нескольких объявлений для «символ»  
  
 Объявление вызывает один и тот же элемент дважды определен.  
  
 Следующий пример приводит к возникновению ошибки C2874:  
  
```  
// C2874.cpp  
namespace Z {  
   int i;  
}  
  
int main() {  
   int i;  
   using Z::i;   // C2874, i already declared  
}  
```