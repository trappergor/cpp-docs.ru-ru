---
title: "Ошибка компилятора C2745 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2745
dev_langs: C++
helpviewer_keywords: C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d1eafe372c3acf8cc824e49066d2fd2c29fc0a88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2745"></a>Ошибка компилятора C2745
«токен»: этот токен не может преобразовать в идентификатор  
  
 Идентификаторы должны состоять из допустимых символов.  
  
 Следующий пример приводит к возникновению ошибки C2745:  
  
```  
// C2745.cpp  
// compile with: /clr  
int main() {  
   int __identifier([));   // C2745  
}  
```