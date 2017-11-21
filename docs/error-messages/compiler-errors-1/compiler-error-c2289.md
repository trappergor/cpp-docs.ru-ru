---
title: "Ошибка компилятора C2289 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2289
dev_langs: C++
helpviewer_keywords: C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6c771780ad3bbaefd51be10c9ff1454127f8439b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2289"></a>Ошибка компилятора C2289
Множественное использование одного и того же квалификатора типа  
  
 В объявлении типа или определении квалификатор типа (`const`, `volatile`, `signed`или `unsigned`) используется более одного раза, что вызывает ошибку совместимости ANSI(**/Za**).  
  
 При компиляции следующего примера возникнет ошибка C2286:  
  
```  
// C2289.cpp  
// compile with: /Za /c  
volatile volatile int i;   // C2289  
volatile int j;   // OK  
```