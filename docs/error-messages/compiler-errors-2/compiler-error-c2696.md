---
title: "Ошибка компилятора C2696 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: 12
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 08b8a7990efbf981aec342b99bbb558fd9fab8d5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2696"></a>Ошибка компилятора C2696
Не удается создать временный объект управляемого типа «тип»  
  
Ссылки на `const` в неуправляемой программе заставляют компилятор вызывает конструктор и создание временного объекта в стеке. Тем не менее управляемого класса не могут создаваться в стеке.  
  
C2696 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  

