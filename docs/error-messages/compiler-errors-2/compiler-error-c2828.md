---
title: "Ошибка компилятора C2828 | Microsoft Docs"
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
  - "C2828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2828"
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

оператор "оператор" не может быть глобально переопределен бинарной формой  
  
 Оператор не может иметь двоичную форму за пределами объекта.  
  
### Возможные способы устранения данной ошибки  
  
1.  Сделайте перегруженный оператор локальным по отношению к объекту.  
  
2.  Выберите для перегрузки подходящий унарный оператор.