---
title: "Ошибка компилятора C3859 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3859
dev_langs:
- C++
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: 9
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
ms.openlocfilehash: 45a653e308422d469817b056eb2a7b80a6fee7b7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3859"></a>Ошибка компилятора C3859
превышен диапазон адресов виртуальной памяти для PCH; повторите компиляцию с параметром командной строки "-Zmvalue" или большим  
  
 Предкомпилированный заголовок слишком мал для объема данных, который компилятор пытается в него поместить. Используйте **/Zm** флаг компилятора, чтобы указать большее значение для предкомпилированного файла заголовка. Дополнительные сведения см. в разделе [/Zm (укажите предкомпилированный заголовок предел выделения памяти)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).
