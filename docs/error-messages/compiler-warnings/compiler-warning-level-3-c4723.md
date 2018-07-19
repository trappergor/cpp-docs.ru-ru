---
title: Предупреждение (уровень 3) C4723 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4723
dev_langs:
- C++
helpviewer_keywords:
- C4723
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c5f91bbdc60ab1901c4afe4d5bea9f3258692ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296618"
---
# <a name="compiler-warning-level-3-c4723"></a>Предупреждение компилятора (уровень 3) C4723
возможное деление на 0  
  
 Второй операнд в операции деления на ноль во время компиляции, что дает неопределенные результаты.  
  
 Это предупреждение выдается только при использовании [/Og](../../build/reference/og-global-optimizations.md) или параметра оптимизации, который подразумевает /Og.  
  
 Компилятор мог создать операнд, равный нулю.