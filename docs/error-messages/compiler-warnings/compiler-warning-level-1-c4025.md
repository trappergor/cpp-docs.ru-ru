---
title: Предупреждение (уровень 1) C4025 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4025
dev_langs:
- C++
helpviewer_keywords:
- C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e84ba11c7bed7420a9a1c699361612ef2002d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4025"></a>Предупреждение компилятора (уровень 1) C4025
"число": относительный указатель передан в функцию с аргументами-переменными: параметр <номер>  
  
 Передача относительного указателя в функцию с аргументами-переменными нормализует указатель с непредвиденными результатами. Не передавайте относительные указатели в функции с аргументами-переменными.