---
title: "Предупреждение (уровень 2) C4653 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4653
dev_langs:
- C++
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8eb855e1c11136cd88c1c1e796d9759581e3ceb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4653"></a>Предупреждение компилятора (уровень 2) C4653
параметр компилятора «параметр» несовместим с предкомпилированным заголовком; текущий параметр командной строки пропускается  
  
 Параметр, заданный с использование предкомпилированных заголовков ([/Yu](../../build/reference/yu-use-precompiled-header-file.md)) параметр несовместим с параметрами, заданными во время создания предкомпилированного заголовка. Этой компиляции используется параметр, заданный при создании предкомпилированного заголовка.  
  
 Это предупреждение может возникать, если другое значение для параметра пакета структуры ([/Zp](../../build/reference/zp-struct-member-alignment.md)) был указан во время компиляции предкомпилированного заголовка.