---
title: "Создание элемента управления Tab | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
dev_langs: C++
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db477a8966e7a7ec5368e5ed9e783b466acbf103
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-tab-control"></a>Создание элемента управления "Вкладка"
Способ создания вкладок элемента управления зависит от того, с помощью элемента управления в диалоговом окне или его создания в окне nondialog.  
  
### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>Использование CTabCtrl непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон Добавление элемента управления Tab ваш ресурс шаблона диалоговых окон. Указать его идентификатор элемента управления.  
  
2.  Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) для добавления переменной-члена типа [CTabCtrl](../mfc/reference/ctabctrl-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CTabCtrl` функции-члены.  
  
3.  Сопоставление функции обработчика в класс диалоговых окон для любого уведомляющих сообщений элемента управления tab, необходимые для обработки. Дополнительные сведения см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).  
  
4.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), установка стилей для `CTabCtrl`.  
  
### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>Для использования в окне nondialog CTabCtrl  
  
1.  Определение элемента управления в классе представления или окна.  
  
2.  Вызов элемента управления [создать](../mfc/reference/ctabctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже в родительское окно [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Установка стилей для элемента управления.  
  
 После `CTabCtrl` объект был создан, можно установить или снять следующие расширенные стили:  
  
-   **TCS_EX_FLATSEPARATORS** прорисовывает управления "Вкладка" разделители между элементов вкладки. Это расширенный стиль только влияет на вкладке элементов управления, имеющих **TCS_BUTTONS** и **TCS_FLATBUTTONS** стили. По умолчанию создание вкладок с **TCS_FLATBUTTONS** стиль задает расширенный стиль.  
  
-   **TCS_EX_REGISTERDROP** управления "Вкладка" приводит к возникновению ошибки **TCN_GETOBJECT** уведомляющих сообщений для запроса объекта-приемника объекта, когда объект перетаскивается через элементы вкладки в элементе управления.  
  
    > [!NOTE]
    >  Для получения **TCN_GETOBJECT** уведомления, необходимо инициализировать библиотеки OLE с помощью вызова [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit).  
  
 Эти стили можно получить и задать после создания элемента управления, с вызовами соответствующих [GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) и [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) функции-члены.  
  
 Например, задать **TCS_EX_FLATSEPARATORS** стиля с помощью следующего фрагмента кода:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]  
  
 Очистить **TCS_EX_FLATSEPARATORS** стиля в `CTabCtrl` объекта с помощью следующего фрагмента кода:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]  
  
 Это приведет к удалению разделителей, стоящих между кнопок вашей `CTabCtrl` объекта.  
  
## <a name="see-also"></a>См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

