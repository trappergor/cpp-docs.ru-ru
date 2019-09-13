---
title: Создание классов диалоговых окон
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: 424d18196063456245e2a4841b42e6e447bded17
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907329"
---
# <a name="creating-your-dialog-class"></a>Создание классов диалоговых окон

Для каждого диалогового окна в программе создайте новый класс диалогового окна для работы с ресурсом диалогового окна.

[Добавление класса](../ide/adding-a-class-visual-cpp.md) объясняет, как создать новый класс диалогового окна. При создании класса диалогового окна с помощью [мастера классов](reference/mfc-class-wizard.md)он записывает следующие элементы в h-и CPP-файлы, указанные ниже.

В h файл:

- Объявление класса для диалогового класса. Класс является производным от класса [CDialog](../mfc/reference/cdialog-class.md).

В cpp – файле:

- Схема сообщений для класса.

- Стандартный конструктор для диалогового окна.

- Переопределение функции члена [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) . Измените эту функцию. Он используется для обмена данными диалоговых окон и проверки, как описано далее в разделе [Обмен и проверка данных диалоговых окон](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>См. также

[Создание класса диалогового окна с помощью мастеров кода](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)
