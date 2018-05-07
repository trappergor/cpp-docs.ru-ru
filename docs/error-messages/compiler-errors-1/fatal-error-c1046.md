---
title: Неустранимая ошибка C1046 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1046
dev_langs:
- C++
helpviewer_keywords:
- C1046
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02c609d5f846fa6f339eac98b725919560df068f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1046"></a>Неустранимая ошибка C1046
ограничение компилятора: недопустимая степень вложения структуры  
  
 Структуры, объединения или класса превышает предел уровней вложенности, 15 уровней. Измените определение или уменьшите уровень вложенности. Разбить на несколько частей структуры, объединения или класса с помощью `typedef` для определения одной или нескольких вложенных структур.