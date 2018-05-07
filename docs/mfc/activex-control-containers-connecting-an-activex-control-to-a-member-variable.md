---
title: 'Контейнеры элементов управления ActiveX: Соединение элемента управления ActiveX с переменной-членом | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06a2b6a5ab17db7b512f1f44d2eda68169d71645
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>Контейнеры элементов управления ActiveX. Соединение элемента управления ActiveX с переменной-членом
Чтобы связать элемент управления ActiveX с переменной-члена класса диалогового окна, который будет содержать элемент управления является самым простым способом доступа к элемента управления ActiveX в пределах его приложение контейнера элемента управления.  
  
> [!NOTE]
>  Это не единственный способ доступа к внедренный элемент управления из внутри класса контейнера, но для целей данной статьи является достаточным.  
  
### <a name="adding-a-member-variable-to-the-dialog-class"></a>Добавление переменной-члена в класс диалоговых окон  
  
1.  Из представления классов щелкните правой кнопкой мыши класс диалогового окна, чтобы открыть контекстное меню. Например, `CContainerDlg`.  
  
2.  В контекстном меню щелкните **добавить** и затем **добавить переменную**.  
  
3.  В мастере добавления члена переменной, щелкните **управляющей переменной**.  
  
4.  В **идентификатор элемента управления** выберите идентификатор элемента управления внедренный элемент управления ActiveX. Например, `IDC_CIRCCTRL1`.  
  
5.  В **имя переменной** введите имя.  
  
     Например, `m_circctl`.  
  
6.  Нажмите кнопку **Готово** принимать параметры и закрыть мастер добавления переменной-члена.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

