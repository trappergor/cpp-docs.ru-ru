---
title: Печать
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: 3d2ef494be66171cbcbf2b8b9e19c29c8bdc5c2f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619805"
---
# <a name="printing"></a>Печать

Microsoft Windows реализует аппаратно-независимые дисплеи. В MFC это означает, что одни и те же вызовы рисования в `OnDraw` функции члена класса представления отвечают за рисование на экране и на других устройствах, таких как принтеры. Для предварительного просмотра конечным устройством выводится имитация вывода на печать.

## <a name="your-role-in-printing-vs-the-frameworks-role"></a><a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>Роль в печати и роли платформы

Класс представления имеет следующие обязанности:

- Сообщите платформе, сколько страниц находится в документе.

- При появлении запроса на печать указанной страницы Нарисуйте эту часть документа.

- Выделение и освобождение любых шрифтов или других ресурсов GDI, необходимых для печати.

- При необходимости перед печатью данной страницы необходимо отправить все управляющие коды, необходимые для изменения режима печати, например, чтобы изменить ориентацию печати для отдельных страниц.

Ниже перечислены обязанности платформы.

- Отображение диалогового окна **Печать** .

- Создайте объект [CDC](reference/cdc-class.md) для принтера.

- Вызовите функции члена [стартдок](reference/cdc-class.md#startdoc) и [енддок](reference/cdc-class.md#enddoc) `CDC` объекта.

- Многократно вызывайте функцию-член [StartPage](reference/cdc-class.md#startpage) `CDC` объекта, сообщите классу представления, какую страницу следует напечатать, и вызовите функцию-член [EndPage](reference/cdc-class.md#endpage) `CDC` объекта.

- Вызывайте переопределяемые функции в представлении в соответствующее время.

В следующих статьях объясняется, как платформа поддерживает печать и предварительный просмотр.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Печать по умолчанию](how-default-printing-is-done.md)

- [Многостраничные документы](multipage-documents.md)

- [Верхние и нижние колонтитулы](headers-and-footers.md)

- [Выделение ресурсов GDI для печати](allocating-gdi-resources.md)

- [Предварительный просмотр](print-preview-architecture.md)

## <a name="see-also"></a>См. также раздел

[Печать и предварительный просмотр печати](printing-and-print-preview.md)
