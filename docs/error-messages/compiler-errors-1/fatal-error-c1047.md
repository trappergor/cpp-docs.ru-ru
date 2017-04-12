---
title: "Неустранимая ошибка C1047 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1047
dev_langs:
- C++
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: 5
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 5b23d0dd38806e613f0066002cc73b143956225c
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1047"></a>Неустранимая ошибка C1047
Файл объекта или библиотеки "файл" был создан с более старой версией компилятора, чем другие объекты; выполните заново построение старых объектов и библиотек  
  
 Ошибка C1047 возникает в процессе компоновки файлов объектов или библиотек, собранных с помощью **/LTCG** , но только в тех случаях, когда для сборки этих объектных файлов или библиотек использовались разные версии набора инструментов Visual C++.  
  
 Это может произойти, если перейти к использованию новой версии компилятора, не выполнив заново сборку существующих объектных файлов или библиотек.  
  
 Чтобы устранить ошибку C1047, необходимо заново выполнить сборку всех объектных файлов и библиотек.
