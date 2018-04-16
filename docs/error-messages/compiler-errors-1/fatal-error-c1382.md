---
title: Неустранимая ошибка C1382 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 923cc957dd136147a6c749f5ebf9508ca7e2052d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1382"></a>Неустранимая ошибка C1382
PCH-файл «файл» был перестроен с момента создания «объект». Повторите построение этого объекта  
  
 При использовании [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), обнаружен PCH-файл новее, чем CIL OBJ-файл, который указывает на нее. Сведения в OBJ-файле CIL-ФАЙЛ является устаревшим. Построение объекта.  
  
 Ошибка C1382 также возникает при компиляции с **/Yc**, но также передается несколько файлов исходного кода для компилятора.  Чтобы решить, следует использовать **/Yc** при передаче нескольких файлов исходного кода для компилятора.  Дополнительные сведения см. в разделе [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md).