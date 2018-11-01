---
title: Регистрация классов Window
ms.date: 11/04/2016
f1_keywords:
- WndProc
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
ms.openlocfilehash: c1fc6628b2b5e8e6fa657f4cf99be2256377a5b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540586"
---
# <a name="registering-window-classes"></a>Регистрация классов Window

Окно «classes» в традиционном программировании для Windows определяющие характеристики используется «class» (а не класс C++), из которого можно создать любое количество windows. Этот тип класса — это шаблон или модель для создания windows.

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Регистрация класса Window в традиционных программ для Windows

В традиционной программы для Windows, без использования MFC, обрабатываются все сообщения в окно в «процедуры окна» или "`WndProc`.» Объект `WndProc` связана с окном, с помощью процесса «регистрация класса window». Зарегистрировано в главном окне `WinMain` функция, но другие классы windows можно зарегистрировать в любом месте в приложении. Регистрации зависит от структуры, которая содержит указатель на `WndProc` работать вместе с спецификации для курсора, кисть фона и т. д. Структура передается в качестве параметра, а также строковое имя класса, в предыдущем вызове `RegisterClass` функции. Таким образом класс регистрации может совместно использоваться несколькими окнами.

## <a name="window-class-registration-in-mfc-programs"></a>Регистрация класса окна в приложениях MFC

Напротив большинство действий по регистрации класса окна выполняется автоматически в приложении платформы MFC. Если вы используете MFC, обычно вы наследуете класс окна C++ из существующего класса библиотеки с помощью обычного синтаксиса C++ для наследования классов. Инфраструктура по-прежнему использует традиционный «регистрации classes», а также стандартные обработчики, зарегистрированные для вас при необходимости. Регистрация классов можно зарегистрировать, вызвав [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) глобальную функцию и передав зарегистрированного класса для `Create` функцию-член `CWnd`. Как описано здесь, традиционные «регистрация класса» в Windows — это не следует путать с класса C++.

Дополнительные сведения см. в разделе [технические Примечание 1](../mfc/tn001-window-class-registration.md).

## <a name="see-also"></a>См. также

[Создание окон](../mfc/creating-windows.md)

