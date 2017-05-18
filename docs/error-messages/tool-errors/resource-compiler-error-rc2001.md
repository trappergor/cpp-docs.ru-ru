---
title: "Ошибка компилятора ресурсов RC2001 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: 6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ba9e855e61af80d29a682738a3f04377f49b6bdf
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="resource-compiler-error-rc2001"></a>Ошибка компилятора ресурсов RC2001
newline в константе  
  
 Строковая константа была продолжена на второй строке без либо обратную косую черту (**\\**) или закрытия и открытия двойные кавычки (**»**).  
  
 Прервать строковую константу на две строки в исходном файле, выполните одно из следующих действий.  
  
-   Закончить первую строку символом продолжения строки обратную косую черту.  
  
-   Строки в первой строке с двойной кавычкой закрыть и открыть строку на следующую строку другими двойными кавычками.  
  
 Недостаточно завершить первую строку escape-последовательность для внедрения символ новой строки в строковую константу "\n".
