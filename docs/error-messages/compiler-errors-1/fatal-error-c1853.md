---
title: "Неустранимая ошибка C1853 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05c29c266aad095517734fdcac776e12467d34ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1853"></a>Неустранимая ошибка C1853
  
> "*filename*" файла предкомпилированного заголовка с предыдущей версии компилятора или предкомпилированный заголовок — C++ и используется из C (или наоборот)  
  
Возможные причины:  
  
-   Предкомпилированный заголовок был скомпилирован с помощью предыдущей версии компилятора. Попробуйте перекомпилировать заголовок с помощью текущего компилятора.  
  
-   — Предкомпилированный заголовок C++ и его использовании в C. Попробуйте перекомпилировать заголовок для использования в C, указав одно из [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) параметры компилятора, или измените суффикс исходного файла на «c». Дополнительные сведения см. в разделе [два варианта предварительной компиляции кода](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).