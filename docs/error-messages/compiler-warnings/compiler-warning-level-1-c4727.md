---
title: Предупреждение (уровень 1) C4727 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4727
dev_langs:
- C++
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c92e42fe275f821e333a0f04a116034a5bb849a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4727"></a>Предупреждение компилятора (уровень 1) C4727
«Предкомпилированного Заголовка с именем pch_file и одинаковой отметкой времени в "Объектном_файле_1" и "объектном_файле_2".  Используется первый PCH-ФАЙЛ.  
  
 C4727 возникает при компиляции нескольких единиц компиляции с **/Yc**, и где компилятору не удалось пометить все OBJ-файлы одинаковой меткой времени PCH.  
  
 Для решения необходимо компилировать один исходный файл с **/Yc /c** (создается предкомпилированного заголовка), и остальные файлы компилировать отдельно с **/Yu /c** (использующим pch), затем связать их друг с другом.  
  
 Таким образом, если выполнена следующая и приводит к возникновению ошибки C4727:  
  
 **CL/CLR /GL a.cpp b.cpp c.cpp /Ycstdafx.h**  
  
 Сделайте следующее вместо:  
  
 **CL/CLR /GL a.cpp /Ycstdafx.h /c**  
  
 **CL/CLR /GL b.cpp c.cpp /Yustdafx.h/Link a.obj**  
  
 Дополнительные сведения см. в разделе .  
  
-   [/Yc (создание предкомпилированного файла заголовка)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (использование файла предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md)