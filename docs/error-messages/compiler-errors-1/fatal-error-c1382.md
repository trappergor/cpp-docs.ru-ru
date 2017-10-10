---
title: "Неустранимая ошибка C1382 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ddb016e14b01b3bc1dfd45c7d5a8ad1aa489ac3a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1382"></a>Неустранимая ошибка C1382
PCH-файл «файл» был перестроен с момента создания «объект». Повторите построение этого объекта  
  
 При использовании [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), обнаружен PCH-файл новее, чем CIL OBJ-файл, который указывает на нее. Сведения в OBJ-файле CIL-ФАЙЛ является устаревшим. Построение объекта.  
  
 Ошибка C1382 также возникает при компиляции с **/Yc**, но также передается несколько файлов исходного кода для компилятора.  Чтобы решить, следует использовать **/Yc** при передаче нескольких файлов исходного кода для компилятора.  Дополнительные сведения см. в разделе [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md).
