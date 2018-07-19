---
title: Предупреждение (уровень 1) C4651 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0015102a44b71f342b125532d20849590157ee0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283371"
---
# <a name="compiler-warning-level-1-c4651"></a>Предупреждение компилятора (уровень 1) C4651
«Определение» указан для предкомпилированного заголовка, но не для текущей компиляции  
  
 Определение был указан при предкомпилированного заголовка, но не в этой компиляции.  
  
 Определение будет действовать внутри предкомпилированного заголовка, но не в остальной части кода.  
  
 Если используется предкомпилированный заголовок был построен с помощью/DSYMBOL, компилятор создает это предупреждение, если компиляции /Yu отсутствует значение/DSYMBOL.  Добавление в командную строку /Yu значение/DSYMBOL разрешает это предупреждение.