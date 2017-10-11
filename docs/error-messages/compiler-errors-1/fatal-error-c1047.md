---
title: "Неустранимая ошибка C1047 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b848f874f382e3d4f944a7eb372db9dcc5011f59
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1047"></a>Неустранимая ошибка C1047
Файл объекта или библиотеки "файл" был создан с более старой версией компилятора, чем другие объекты; выполните заново построение старых объектов и библиотек  
  
 Ошибка C1047 возникает в процессе компоновки файлов объектов или библиотек, собранных с помощью **/LTCG** , но только в тех случаях, когда для сборки этих объектных файлов или библиотек использовались разные версии набора инструментов Visual C++.  
  
 Это может произойти, если перейти к использованию новой версии компилятора, не выполнив заново сборку существующих объектных файлов или библиотек.  
  
 Чтобы устранить ошибку C1047, необходимо заново выполнить сборку всех объектных файлов и библиотек.
