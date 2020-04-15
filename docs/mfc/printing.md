---
title: Печать
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: a46096592c9983d04d2122bfabb56ece9346c4bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371195"
---
# <a name="printing"></a>Печать

Microsoft Windows реализует независимый дисплей. В MFC это означает, что одни `OnDraw` и те же вызовы чертежа, в функции члена класса представления, отвечают за рисование на дисплее и на других устройствах, таких как принтеры. Для предварительного просмотра печати целевое устройство представляет собой смоделированный вывод принтера на дисплее.

## <a name="your-role-in-printing-vs-the-frameworks-role"></a><a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>Ваша роль в печати против роли Рамочной

Класс представления имеет следующие обязанности:

- Сообщите рамоче, сколько страниц в документе.

- Когда его попросят распечатать указанную страницу, нарисуйте эту часть документа.

- Распределение и дераспределение любых шрифтов или других ресурсов интерфейса графических устройств (GDI), необходимых для печати.

- При необходимости отправьте любые коды побега, необходимые для изменения режима принтера перед печатью данной страницы, например, чтобы изменить ориентацию печати на основе на страницу.

Обязанности рамок следующие:

- Отобразите **диалоговую** коробку Print.

- Создайте объект [CDC](../mfc/reference/cdc-class.md) для принтера.

- Позвоните в функции участника [StartDoc](../mfc/reference/cdc-class.md#startdoc) и [EndDoc](../mfc/reference/cdc-class.md#enddoc) `CDC` объекта.

- Неоднократно вызывайте функцию участника `CDC` [StartPage](../mfc/reference/cdc-class.md#startpage) объекта, сообщайте классу представления, какая страница должна `CDC` быть напечатана, и вызывайте функцию члена [EndPage](../mfc/reference/cdc-class.md#endpage) объекта.

- Вызов переизбытываемых функций в представлении в подходящее время.

В следующих статьях обсуждается, как фреймворк поддерживает печать и предварительный просмотр печати:

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Печать по умолчанию](../mfc/how-default-printing-is-done.md)

- [Многостраничные документы](../mfc/multipage-documents.md)

- [Заголовки и колонтитулы](../mfc/headers-and-footers.md)

- [Выделение ресурсов GDI для печати](../mfc/allocating-gdi-resources.md)

- [Предварительный просмотр печати](../mfc/print-preview-architecture.md)

## <a name="see-also"></a>См. также раздел

[Печать и предварительный просмотр печати](../mfc/printing-and-print-preview.md)
