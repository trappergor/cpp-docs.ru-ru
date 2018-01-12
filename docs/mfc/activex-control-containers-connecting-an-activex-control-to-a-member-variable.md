---
title: "Контейнеры элементов управления ActiveX: Соединение элемента управления ActiveX с переменной-членом | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2248dd68b0ecc7471899552bcb7b0394f3f9f363
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

