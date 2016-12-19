---
title: "Ошибка компилятора C2834 | Microsoft Docs"
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
  - "C2834"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2834"
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2834
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operator оператор" должен иметь глобальное полное имя  
  
 Операторы `new` и `delete` связаны со своим классом.  Разрешение области видимости неприменимо для выбора версии оператора `new` или `delete` из другого класса.  Чтобы реализовать несколько форм оператора `new` или `delete`, создайте версию этого оператора с дополнительными формальными параметрами.