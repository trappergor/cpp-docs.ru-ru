---
title: Предупреждение (уровень 1) C4041 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4041
dev_langs:
- C++
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfd8c933522e523329c41ebe666a5a7e3c198cb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4041"></a>Предупреждение компилятора (уровень 1) C4041
ограничение компилятора: завершение вывода браузера  
  
 Информация для браузера превысила установленный для компилятора предел.  
  
 Это предупреждение может быть вызвано компиляцией с параметром [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (информация для браузера включает локальные переменные).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Выполните компиляцию с параметром /Fr (информация для браузера без локальных переменных).  
  
2.  Отключите вывод информации для браузера (выполните компиляцию без параметра /FR или /Fr).