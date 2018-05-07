---
title: Предупреждение (уровень 2) C4653 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4653
dev_langs:
- C++
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c312b7530fa11bb734dc99a872b36e926890f658
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4653"></a>Предупреждение компилятора (уровень 2) C4653
параметр компилятора «параметр» несовместим с предкомпилированным заголовком; текущий параметр командной строки пропускается  
  
 Параметр, заданный с использование предкомпилированных заголовков ([/Yu](../../build/reference/yu-use-precompiled-header-file.md)) параметр несовместим с параметрами, заданными во время создания предкомпилированного заголовка. Этой компиляции используется параметр, заданный при создании предкомпилированного заголовка.  
  
 Это предупреждение может возникать, если другое значение для параметра пакета структуры ([/Zp](../../build/reference/zp-struct-member-alignment.md)) был указан во время компиляции предкомпилированного заголовка.