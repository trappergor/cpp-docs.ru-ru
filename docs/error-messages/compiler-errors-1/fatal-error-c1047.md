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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ddc117d1e83c635bfbc644606c6c8c6032ff4f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1047"></a>Неустранимая ошибка C1047
Файл объекта или библиотеки "файл" был создан с более старой версией компилятора, чем другие объекты; выполните заново построение старых объектов и библиотек  
  
 Ошибка C1047 возникает в процессе компоновки файлов объектов или библиотек, собранных с помощью **/LTCG** , но только в тех случаях, когда для сборки этих объектных файлов или библиотек использовались разные версии набора инструментов Visual C++.  
  
 Это может произойти, если перейти к использованию новой версии компилятора, не выполнив заново сборку существующих объектных файлов или библиотек.  
  
 Чтобы устранить ошибку C1047, необходимо заново выполнить сборку всех объектных файлов и библиотек.