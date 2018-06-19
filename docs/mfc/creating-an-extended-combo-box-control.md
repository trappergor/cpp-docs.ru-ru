---
title: Создание расширенных списком | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6a891aeadf2fa8366eec52a967e13776db6523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341216"
---
# <a name="creating-an-extended-combo-box-control"></a>Создание элементов управления "Расширенное поле со списком"
Как создается элемент управления «Расширенное поле со списком» зависит от того, с помощью элемента управления в диалоговом окне или его создания в окне nondialog.  
  
### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>Использование CComboBoxEx непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон добавьте элемент управления списком расширенных для вашего ресурса шаблона диалогового окна. Указать его идентификатор элемента управления.  
  
2.  Укажите любые стили, требуемое диалоговое окно свойств элемента управления Расширенное поле со списком.  
  
3.  Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) для добавления переменной-члена типа [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CComboBoxEx` функции-члены.  
  
4.  Используйте окно свойств для сопоставления функции обработчика в класс диалоговых окон для любого Расширенное поле со списком поле уведомляющих сообщений элемента управления при необходимости обработки (см. [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), задайте любые дополнительные стили для `CComboBoxEx` объекта.  
  
### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>Использование CComboBoxEx в окне nondialog  
  
1.  Определение элемента управления в классе представления или окна.  
  
2.  Вызов элемента управления [создать](../mfc/reference/ctabctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже в родительское окно [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция-обработчик. Установка стилей для элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Использование CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Элементы управления](../mfc/controls-mfc.md)

