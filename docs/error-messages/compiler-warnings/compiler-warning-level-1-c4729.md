---
title: Предупреждение (уровень 1) C4729 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4729
dev_langs:
- C++
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02ccbb80a44123498a231c1909c9c2c6fca72a24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4729"></a>Предупреждение компилятора (уровень 1) C4729
слишком большая функция для предупреждений, основанных на оптимизации структуры кода  
  
 Это предупреждение возникает в случае, если функция слишком велика для компиляции с надежной проверкой ситуаций, в которых могут возникать предупреждения. Это предупреждение появляется только в том случае, если используется параметр компилятора [/Od](../../build/reference/od-disable-debug.md) .  
  
 Чтобы устранить это предупреждение, разделите функцию на более мелкие функции.