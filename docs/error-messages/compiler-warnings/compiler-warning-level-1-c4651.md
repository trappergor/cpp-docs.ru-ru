---
title: "Предупреждение (уровень 1) C4651 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4651
dev_langs: C++
helpviewer_keywords: C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f1faffc6ba7b9df4fecefa3bef47f0418fdc8641
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4651"></a>Предупреждение компилятора (уровень 1) C4651
«Определение» указан для предкомпилированного заголовка, но не для текущей компиляции  
  
 Определение был указан при предкомпилированного заголовка, но не в этой компиляции.  
  
 Определение будет действовать внутри предкомпилированного заголовка, но не в остальной части кода.  
  
 Если используется предкомпилированный заголовок был построен с помощью/DSYMBOL, компилятор создает это предупреждение, если компиляции /Yu отсутствует значение/DSYMBOL.  Добавление в командную строку /Yu значение/DSYMBOL разрешает это предупреждение.