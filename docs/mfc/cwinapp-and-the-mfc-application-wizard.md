---
title: CWinApp и мастер приложений MFC
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: f57b3b2b37a97093aa6d81b59a12c8cf023e3157
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622942"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp и мастер приложений MFC

При создании каркасного приложения мастер приложений MFC объявляет класс приложения, производный от [CWinApp](reference/cwinapp-class.md). Мастер приложений MFC также создает файл реализации, содержащий следующие элементы:

- Схема сообщений для класса приложения.

- Пустой конструктор класса.

- Переменная, объявляющая один и только объект класса.

- Стандартная реализация `InitInstance` функции-члена.

Класс приложения помещается в заголовок проекта и основные исходные файлы. Имена создаваемых классов и файлов основаны на имени проекта, которое вы используете в мастере приложений MFC. Проще всего Просмотреть код для этих классов с помощью [представление классов](/visualstudio/ide/viewing-the-structure-of-code).

Указанные стандартные реализации и схема сообщений подходят для многих целей, но при необходимости их можно изменить. Наиболее интересным из этих реализаций является функция- `InitInstance` член. Как правило, в реализацию скелетообразных будет добавлен код `InitInstance` .

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](cwinapp-the-application-class.md)<br/>
[Переопределяемые функции членов CWinApp](overridable-cwinapp-member-functions.md)<br/>
[Специальные службы CWinApp](special-cwinapp-services.md)
