---
title: Печать в элементах управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: 671aec27584af975ce1635793ae80879e7208d4b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508001"
---
# <a name="printing-in-rich-edit-controls"></a>Печать в элементах управления "Rich Edit"

Чтобы отобразить выходные данные для указанного устройства (например, принтера), можно указать форматированный элемент управления Editing ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Можно также указать выходное устройство, для которого элемент управления "поле редактирования" форматирует свой текст.

Чтобы форматировать часть содержимого элемента управления Rich Edit для конкретного устройства, можно использовать функцию-член [форматранже](../mfc/reference/cricheditctrl-class.md#formatrange) . Структура [форматранже](/windows/win32/api/richedit/ns-richedit-formatrange) , используемая с этой функцией, определяет диапазон текста для форматирования, а также контекст устройства (DC) для целевого устройства.

После форматирования текста для устройства вывода можно отправить выходные данные на устройство с помощью функции члена [дисплайбанд](../mfc/reference/cricheditctrl-class.md#displayband) . Многократно используя `FormatRange` и `DisplayBand`, приложение, которое выводит содержимое элемента управления Rich Edit, может реализовать чередование. (Чередование — это подразделение выходных данных на небольшие части для печати.)

Вы можете использовать функцию-член [сеттаржетдевице](../mfc/reference/cricheditctrl-class.md#settargetdevice) , чтобы указать целевое устройство, для которого форматируемый элемент управления редактирования форматирует свой текст. Эта функция полезна для режима WYSIWYG (то, что вы видите, что вы получаете), в котором приложение позиционирует текст, используя метрики шрифта принтера по умолчанию вместо экрана.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
