---
title: "Предупреждение (уровень 1) C4627 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a435eef7397eb98ca500be1c99e92efcb55c8be6
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4627"></a>Предупреждение компилятора (уровень 1) C4627
"\<идентификатор настроек": пропущен при поиске использования предкомпилированного заголовка  
  
 При поиске расположения, где используется предкомпилированный заголовок, компилятор обнаружил `#include` директивы *\<идентификатор настроек* включаемого файла. Компилятор игнорирует `#include` директивы, но выдает предупреждение **C4627** если предкомпилированный заголовок еще не содержит *\<идентификатор настроек* включаемого файла.  
  
## <a name="see-also"></a>См. также  
 [Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)
