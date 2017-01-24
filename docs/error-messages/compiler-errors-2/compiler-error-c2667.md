---
title: "Ошибка компилятора C2667 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2667"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2667"
ms.assetid: 3c91d9d1-18fa-4e0d-a9ba-984d38980ca3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2667
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": нет перегрузок, имеющих лучшее преобразование  
  
 Вызов перегруженной функции является неоднозначным и не может быть разрешен.  
  
 Преобразование, необходимое для совпадения фактических параметров в вызове одной перегруженной функции, должно быть строго лучше, чем преобразования, требуемые всеми другими перегруженными функциями.  
  
 Дополнительные сведения о частичном упорядочивании шаблонов функций см. в статье базы знаний Q240869.