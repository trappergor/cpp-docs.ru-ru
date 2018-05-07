---
title: Создание классов диалоговых окон | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d70f27639344fd00a2e99ad79bf2db166f3270a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-your-dialog-class"></a>Создание классов диалоговых окон
В каждом диалоговом в программе создайте новый класс диалогового окна для работы с ресурса диалогового окна.  
  
 [Добавление класса](../ide/adding-a-class-visual-cpp.md) описывается создание нового класса диалогового окна. При создании класса диалогового окна с помощью мастера добавления класса записывает следующие элементы. H и. CPP-файлов, которые можно указать:  
  
 В. H-файл:  
  
-   Объявление класса для класса диалогового окна. Класс, производный от [CDialog](../mfc/reference/cdialog-class.md).  
  
 В. CPP-файл:  
  
-   Сопоставление сообщений для класса.  
  
-   Стандартный конструктор для диалогового окна.  
  
-   Переопределение [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) функции-члена. Измените эту функцию. Он используется для возможности обмена и проверки данных диалогового окна, как описано в дальнейшем [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md).  
  
## <a name="see-also"></a>См. также  
 [Создание класса диалогового окна с помощью мастеров кода](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

