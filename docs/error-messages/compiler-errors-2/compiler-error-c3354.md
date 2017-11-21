---
title: "Ошибка компилятора C3354 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3354
dev_langs: C++
helpviewer_keywords: C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e4fc95051f9a59db0fcb06fd4990637efda34516
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3354"></a>Ошибка компилятора C3354
"функция": функция, используемая для создания делегата, не может иметь тип возврата "тип"  
  
 Следующие типы недопустимы в качестве типов возврата для `delegate`:  
  
-   Указатель на функцию  
  
-   Указатель на член  
  
-   Указатель на функцию-член  
  
-   Ссылка на функцию  
  
-   Ссылка на функцию-член  
  
 В следующем примере возникает ошибка C3354:  
  
```  
// C3354_2.cpp  
// compile with: /clr /c  
using namespace System;  
typedef void ( *VoidPfn )();  
  
delegate VoidPfn func(); // C3354  
// try the following line instead  
// delegate  void func();  
```  
