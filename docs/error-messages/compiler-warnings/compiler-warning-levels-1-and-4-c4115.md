---
title: "Предупреждение (уровни 1 и 4) C4115 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4115
dev_langs:
- C++
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
caps.latest.revision: 6
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
ms.openlocfilehash: bcddaf9da3fd05d66e219ec2134799bc49e30f9d
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Предупреждение компилятора (уровни 1 и 4) C4115
"тип": определение именованного типа в круглых скобках  
  
 Указанный символ используется для определения структуры, объединения или перечисляемого типа в выражении в скобках. Область определения может быть непредусмотренной.  
  
 В вызове функции C определение имеет глобальную область. В вызове C++ определение имеет ту же область, что и вызываемая функция.  
  
 Это предупреждение также может быть вызвано деклараторами внутри скобок (такими как прототипы), которые не являются выражениями в скобках.  
  
 Это предупреждение уровня 1 для программ C++ и программ C, скомпилированных в режиме совместимости с ANSI (/Za). В противном случае оно имеет уровень 3.
