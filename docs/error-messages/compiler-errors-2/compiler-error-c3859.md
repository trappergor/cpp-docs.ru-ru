---
title: "Ошибка компилятора C3859 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8a132eb7dbf09421ad5c99249b0208e5f901156b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3859"></a>Ошибка компилятора C3859
превышен диапазон адресов виртуальной памяти для PCH; повторите компиляцию с параметром командной строки "-Zmvalue" или большим  
  
 Предкомпилированный заголовок слишком мал для объема данных, который компилятор пытается в него поместить. Используйте **/Zm** флаг компилятора, чтобы указать большее значение для предкомпилированного файла заголовка. Дополнительные сведения см. в разделе [/Zm (укажите предкомпилированный заголовок предел выделения памяти)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).
