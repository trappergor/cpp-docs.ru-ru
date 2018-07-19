---
title: Неустранимая ошибка NMAKE U1051 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 570c7e5d8e6e8250a67e4f032ac26b04388cfd00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317418"
---
# <a name="nmake-fatal-error-u1051"></a>Неустранимая ошибка NMAKE U1051
Недостаточно памяти  
  
 NMAKE не хватило памяти, включая виртуальной памяти, поскольку файл makefile слишком большой или сложной.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Освободите место на диске.  
  
2.  Увеличьте размер файла подкачки Windows NT или файл подкачки Windows.  
  
3.  При использовании часть файла makefile только разделите makefile отдельные файлы или использовать **! Если** директивы для ограничения объема, который должен обрабатывать NMAKE препроцессора. **! Если** директивы содержат **! Если**, `!IFDEF`, **! Ifndef:**, **! ELSE IF**, **! ELSE** `IFDEF`, и **! ELSE** `IFNDEF`.