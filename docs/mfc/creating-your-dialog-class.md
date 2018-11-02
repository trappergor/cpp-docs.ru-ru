---
title: Создание классов диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: 924cf2d79056d958aad775f92a6d0df2d45c8a70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536585"
---
# <a name="creating-your-dialog-class"></a>Создание классов диалоговых окон

В каждом диалоговом окне, в приложении создайте новый класс диалогового окна для работы с ресурса диалогового окна.

[Добавление класса](../ide/adding-a-class-visual-cpp.md) описывается создание нового класса диалогового окна. При создании класса диалогового окна с помощью мастера добавления класса, он пишет следующие элементы. H и. CPP-файлов, указываемые:

В. H-файл:

- Объявление класса для класса диалогового окна. Класс, производный от [CDialog](../mfc/reference/cdialog-class.md).

В. CPP-файл:

- Сопоставление сообщений для класса.

- Стандартный конструктор для диалогового окна.

- Переопределение [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) функция-член. Измените эту функцию. Он используется для возможности обмена и проверки данных диалогового окна, как описано далее в [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>См. также

[Создание класса диалогового окна с помощью мастеров кода](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

