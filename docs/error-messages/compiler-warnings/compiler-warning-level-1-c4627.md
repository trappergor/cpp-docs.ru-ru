---
title: Предупреждение (уровень 1) C4627 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcde9e6707465fd95dbcb10e073a852624f0de0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4627"></a>Предупреждение компилятора (уровень 1) C4627
"\<идентификатор >": пропущен при поиске использования предкомпилированного заголовка  
  
 При поиске расположения, где используется предкомпилированный заголовок, компилятор обнаружил `#include` директивы  *\<идентификатор >* включаемого файла. Компилятор игнорирует `#include` директивы, но выдает предупреждение **C4627** если предкомпилированный заголовок еще не содержит  *\<идентификатор >* включаемого файла.  
  
## <a name="see-also"></a>См. также  
 [Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)