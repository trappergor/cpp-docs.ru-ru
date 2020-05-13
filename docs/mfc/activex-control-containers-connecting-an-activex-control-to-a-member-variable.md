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
ms.openlocfilehash: 620a9ec58b3a5a8fcdac63626b81fbc4620de399
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371617"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>Контейнеры элементов управления ActiveX. Соединение элемента управления ActiveX с переменной-членом

Самый простой способ получить доступ к управлению ActiveX из своего приложения контейнера управления — связать элемент управления ActiveX с переменной члена класса диалога, которая будет содержать элемент управления.

> [!NOTE]
> Это не единственный способ получить доступ к встроенного элемента управления из класса контейнеров, но для целей данной статьи этого достаточно.

### <a name="adding-a-member-variable-to-the-dialog-class"></a>Добавление переменной участника в класс диалогов

1. От класса View, право йнюк основной класс диалога, чтобы открыть меню ярлыка. Например, `CContainerDlg`.

1. Из меню ярлыка, нажмите **Добавить,** а затем **добавить переменной**.

1. В переменном мастере добавления участника щелкните **переменной управления.**

1. В поле списка **идентификатора управления** выберите идентификатор управления встроенным элементом управления ActiveX. Например, `IDC_CIRCCTRL1`.

1. В поле **переменного имени** введите имя.

   Например, *m_circctl*.

1. Нажмите **Закончить,** чтобы принять ваш выбор и выйти из Добавить член переменный мастер.

## <a name="see-also"></a>См. также раздел

[Контейнеры управления ActiveX](../mfc/activex-control-containers.md)
