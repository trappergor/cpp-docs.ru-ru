---
title: Предупреждение компилятора (уровень 1) C4727 | Документация Майкрософт
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
ms.openlocfilehash: b9d169ec9d08f06831370fa68c4049076dbfc582
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053743"
---
# <a name="compiler-warning-level-1-c4727"></a>Предупреждение компилятора (уровень 1) C4727

«PCH-ФАЙЛ с именем pch_file с одинаковой меткой времени в "Объектном_файле_1" и "объектном_файле_2".  Используется первый PCH.

C4727 возникает при компиляции нескольких единиц компиляции с **/Yc**, и где компилятору удалось все OBJ-файлы с одинаковой меткой времени PCH.

Чтобы устранить ошибку, компиляцию один исходный файл с **/Yc /c** (создание предкомпилированного заголовка), и остальные отдельно компиляцию с параметром **/Yu /c** (использует pch), связать их вместе.

Таким образом, если выполнена следующая и приводит к возникновению ошибки C4727:

**CL/CLR /GL a.cpp b.cpp c.cpp /Ycstdafx.h**

Можно выполнить следующие вместо:

**CL/CLR /GL a.cpp /Ycstdafx.h /c**

**CL/CLR /GL b.cpp c.cpp /Yustdafx.h/Link a.obj**

Дополнительные сведения см. в разделе .

- [/Yc (создание предкомпилированного файла заголовка)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (использование файла предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md)