---
title: CWinApp и мастер приложений MFC
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: 1a46842d7b4d6a588da585d63e2ad56982bb0ff8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447038"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp и мастер приложений MFC

При создании каркасного приложения мастер приложений MFC объявляет класс приложения, производный от [CWinApp](../mfc/reference/cwinapp-class.md). Мастер приложений MFC также создает файл реализации, содержащий следующие элементы:

- Схема сообщений для класса приложения.

- Пустой конструктор класса.

- Переменная, объявляющая один и только объект класса.

- Стандартная реализация функции-члена `InitInstance`.

Класс приложения помещается в заголовок проекта и основные исходные файлы. Имена создаваемых классов и файлов основаны на имени проекта, которое вы используете в мастере приложений MFC. Проще всего Просмотреть код для этих классов с помощью [представление классов](/visualstudio/ide/viewing-the-structure-of-code).

Указанные стандартные реализации и схема сообщений подходят для многих целей, но при необходимости их можно изменить. Наиболее интересным из этих реализаций является функция-член `InitInstance`. Как правило, код добавляется в реализацию скелетообразных `InitInstance`.

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)<br/>
[Переопределяемые функции-члены CWinApp](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Специальные службы CWinApp](../mfc/special-cwinapp-services.md)
