---
title: "Ошибка средств компоновщика LNK2013 | Microsoft Docs"
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
  - "LNK2013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2013"
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK2013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

тип привязки вызывает сегментное переполнение.Целевое имя "symbol name" вне диапазона  
  
 Компоновщик может не соответствовать необходимому адресу или интервалу в данной инструкции, поскольку целевой символ находится слишком далеко от расположения инструкции.  
  
 Можно разрешить эту проблему созданием нескольких изображений или используя параметр [\/ORDER](../../build/reference/order-put-functions-in-order.md) так, чтобы инструкция и целевое имя были ближе друг к другу.  
  
 Если имя символа определено пользователем \(а не создано компилятором\), то для разрешения ошибки можно выполнить следующие действия:  
  
-   Измените статическую функцию на нестатическую.  
  
-   Переименуйте раздел кода, содержащий статическую функцию, так, чтобы этот раздел имел имя вызывающего.  
  
 Чтобы определить является ли функция статической, используйте `DUMPBIN /SYMBOLS`.