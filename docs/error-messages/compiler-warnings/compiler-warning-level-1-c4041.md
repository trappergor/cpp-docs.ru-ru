---
title: "Предупреждение (уровень 1) C4041 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4041
dev_langs: C++
helpviewer_keywords: C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2ae98391c3c5bfb603afae684027a86c39c840b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4041"></a>Предупреждение компилятора (уровень 1) C4041
ограничение компилятора: завершение вывода браузера  
  
 Информация для браузера превысила установленный для компилятора предел.  
  
 Это предупреждение может быть вызвано компиляцией с параметром [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (информация для браузера включает локальные переменные).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Выполните компиляцию с параметром /Fr (информация для браузера без локальных переменных).  
  
2.  Отключите вывод информации для браузера (выполните компиляцию без параметра /FR или /Fr).