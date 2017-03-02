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
caps.latest.revision: 10
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
ms.openlocfilehash: d312a819b5e91386d805635fdd588b72ee842cfe
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1853"></a>Неустранимая ошибка C1853
файл предкомпилированного заголовка «ИмяФайла» предыдущей версии компилятора, или предкомпилированного заголовка является C++ и использовании из C (или наоборот)  
  
 Возможные причины:  
  
-   Предкомпилированный заголовок был создан с помощью предыдущей версии компилятора. Попробуйте перекомпилировать заголовок с помощью текущего компилятора.  
  
-   Предкомпилированный заголовок является C++ и используется в C. Попробуйте перекомпилировать заголовок для использования в C, указав один из [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) параметры компилятора, или измените суффикс исходного файла на «c». Дополнительные сведения см. в разделе [два варианта предварительной компиляции кода](../../build/reference/two-choices-for-precompiling-code.md).
