---
title: "Предупреждение (уровень 1) C4727 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4727
dev_langs:
- C++
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c3d77b053fb866a16e6642ba2e6a24ff6d85798f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4727"></a>Предупреждение компилятора (уровень 1) C4727
«PCH-ФАЙЛ с именем pch_file с одинаковой меткой времени в "Объектном_файле_1" и "объектном_файле_2".  Используется первый PCH-ФАЙЛ.  
  
 Предупреждение C4727 возникает при компиляции нескольких единиц компиляции с **/Yc**, и где компилятору не удалось пометить все OBJ-файлы одинаковой меткой времени PCH.  
  
 Для решения, компилировать один исходный файл с **/Yc /c** (создающим pch), а остальные файлы компилировать отдельно с **/Yu /c** (использующим pch), связать их вместе.  
  
 Таким образом, если выполнена следующая и создает C4727:  
  
 **CL/CLR /GL a.cpp b.cpp c.cpp /Ycstdafx.h**  
  
 Вы бы вместо сделайте следующее:  
  
 **CL/CLR /GL a.cpp /Ycstdafx.h/c**  
  
 **CL/CLR /GL b.cpp c.cpp /Yustdafx.h/Link a.obj**  
  
 Дополнительные сведения см. в разделе .  
  
-   [/Yc (создать предварительно скомпилированный заголовочный файл)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (использование файла предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md)
