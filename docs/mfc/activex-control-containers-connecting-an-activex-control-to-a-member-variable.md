---
title: Контейнеры элементов управления ActiveX. Соединение элемента управления ActiveX с переменной-членом
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
ms.openlocfilehash: 87cb560a1054a912a4e8574cfe2dee74d5e61fe6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625135"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>Контейнеры элементов управления ActiveX. Соединение элемента управления ActiveX с переменной-членом

Самый простой способ доступа к элементу управления ActiveX из приложения контейнера элементов управления заключается в связывании элемента управления ActiveX с переменной-членом класса диалогового окна, который будет содержать элемент управления.

> [!NOTE]
> Это не единственный способ получить доступ к внедренному элементу управления из класса контейнера, но для целей этой статьи это достаточно.

### <a name="adding-a-member-variable-to-the-dialog-class"></a>Добавление переменной-члена в класс диалогового окна

1. В представление классов щелкните правой кнопкой мыши основной класс диалогового окна, чтобы открыть контекстное меню. Например, `CContainerDlg`.

1. В контекстном меню выберите **Добавить** , а затем **Добавить переменную**.

1. В мастере добавления переменной члена щелкните **элемент управления переменная**.

1. В списке **идентификатор элемента управления** выберите идентификатор элемента управления внедренного элемента управления ActiveX. Например, `IDC_CIRCCTRL1`.

1. В поле **имя переменной** введите имя.

   Например, *m_circctl*.

1. Нажмите кнопку **Готово** , чтобы принять выбранные параметры и выйти из мастера добавления переменной члена.

## <a name="see-also"></a>См. также раздел

[Контейнеры элементов управления ActiveX](activex-control-containers.md)
