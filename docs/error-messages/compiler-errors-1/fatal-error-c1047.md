---
title: Неустранимая ошибка C1047 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1047
dev_langs:
- C++
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce88321173ee2c8cc286f18d8ab8f1bf5ec98e13
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198629"
---
# <a name="fatal-error-c1047"></a>Неустранимая ошибка C1047
Файл объекта или библиотеки "файл" был создан с более старой версией компилятора, чем другие объекты; выполните заново построение старых объектов и библиотек  
  
 Ошибка C1047 возникает в процессе компоновки файлов объектов или библиотек, собранных с помощью **/LTCG** , но только в тех случаях, когда для сборки этих объектных файлов или библиотек использовались разные версии набора инструментов Visual C++.  
  
 Это может произойти, если перейти к использованию новой версии компилятора, не выполнив заново сборку существующих объектных файлов или библиотек.  
  
 Чтобы устранить ошибку C1047, необходимо заново выполнить сборку всех объектных файлов и библиотек.