---
title: "Форматирование выходных данных этапа настраиваемого построения или события построения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53720e93c7d45f1eaeb0e62749194720373bee1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Форматирование выходных данных этапа настраиваемого построения или события построения
При правильном форматировании выходных данных этапа настраиваемого построения или события построения пользователи получают следующие преимущества:  
  
-   Предупреждения и ошибки учитываются **вывода** окна.  
  
-   Выходные данные располагаются в **список задач** окна.  
  
-   Щелкнув выходные данные в **вывода** окна отображается соответствующий раздел.  
  
-   F1 включено в **список задач** окна или **вывода** окна.  
  
 Формат вывода должен быть:  
  
 {*filename* (*номер_строки* [, *столбца #*]) &#124; *toolname*} **:**  
  
 [*любой текст*] {**ошибка** &#124; **предупреждение**} *кода ###***:***локализуемые строки*  
  
 [ *любой текст* ]  
  
 Где:  
  
-   {*a* &#124; *b*} — Выбор любого *a* или *b*.  
  
-   [`ccc`] является необязательной строкой или параметром.  
  
 Пример:  
  
 C:\\*sourcefile.cpp*(134): ошибка C2143: синтаксическая ошибка: отсутствует «;» до "}"  
  
 СВЯЗИ: Неустранимая ошибка LNK1104: не удается открыть файл "*somelib.lib*"  
  
## <a name="see-also"></a>См. также  
 [Сведения об этапах настраиваемой сборки и событиях сборки](../ide/understanding-custom-build-steps-and-build-events.md)