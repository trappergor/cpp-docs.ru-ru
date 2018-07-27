---
title: Неустранимая ошибка C1853 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa6a67c13f76b0bf43159b9e9de95068102a2b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229213"
---
# <a name="fatal-error-c1853"></a>Неустранимая ошибка C1853
  
> "*filename*" файла предкомпилированного заголовка с предыдущей версии компилятора или предкомпилированный заголовок — C++ и используется из C (или наоборот)  
  
Возможные причины:  
  
-   Предкомпилированный заголовок был скомпилирован с помощью предыдущей версии компилятора. Попробуйте перекомпилировать заголовок с помощью текущего компилятора.  
  
-   — Предкомпилированный заголовок C++ и его использовании в C. Попробуйте перекомпилировать заголовок для использования в C, указав одно из [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) параметры компилятора, или измените суффикс исходного файла на «c». Дополнительные сведения см. в разделе [два варианта предварительной компиляции кода](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).