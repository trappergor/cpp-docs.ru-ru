---
title: "Ошибка компилятора C2904 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2904
dev_langs: C++
helpviewer_keywords: C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b177a7725b1ed6c411e4ffaebfce34860377e34e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2904"></a>Ошибка компилятора C2904
"идентификатор": имя уже использовано для шаблона в текущей области видимости  
  
 Проверьте наличие повторяющихся имен в коде.  
  
 Следующий пример приводит к возникновению ошибки C2904:  
  
```  
// C2904.cpp  
// compile with: /c  
void X();  // X is declared as a function  
template<class T> class X{};  // C2904  
```