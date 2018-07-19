---
title: Форматирование выходных данных настраиваемого этапа сборки или события сборки | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7da71e6391d2d3223b47ba528686d2fec003ab3a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33321354"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Форматирование выходных данных этапа настраиваемого построения или события построения
Правильное форматирование выходных данных настраиваемого этапа сборки или события сборки дает пользователям следующие преимущества.  
  
-   Предупреждения и ошибки учитываются в окне **Вывод**.  
  
-   Выходные данные отображаются в окне **Список задач**.  
  
-   Если щелкнуть выходные данные в окне **Вывод**, отображается соответствующий раздел.  
  
-   Доступны операции F1 в окне **Список задач** или **Вывод**.  
  
 Выходные данные должны иметь следующий формат:  
  
 {*имя_файла* (*№_строки* [, *№_столбца*]) &#124; *имя_средства*} **:**  
  
 [*любой текст*] {**ошибка** &#124; **предупреждение**} *код####***:*** локализуемые строки*  
  
 [ *любой текст* ]  
  
 Где:  
  
-   {*а* &#124; *б*} — это выбор между *а* и *б*.  
  
-   [`ccc`] — это необязательная строка или необязательный параметр.  
  
 Пример:  
  
 C:\\*sourcefile.cpp*(134) : ошибка C2143: синтаксическая ошибка : отсутствует ";" перед "}"  
  
 ССЫЛКА : неустранимая ошибка LNK1104: не удается открыть файл "*somelib.lib*"  
  
## <a name="see-also"></a>См. также  
 [Сведения об этапах настраиваемой сборки и событиях сборки](../ide/understanding-custom-build-steps-and-build-events.md)