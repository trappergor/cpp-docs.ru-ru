---
title: "Adding Controls to a Dialog Causes the Dialog to No Longer Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], troubleshooting"
  - "common controls, troubleshooting"
  - "troubleshooting controls"
  - "dialog boxes, troubleshooting"
  - "dialog box controls, troubleshooting"
  - "InitCommonControls"
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Adding Controls to a Dialog Causes the Dialog to No Longer Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

После добавления общего общий элемента управления или элемента управления "RichEdit" в диалоговое окно, данный элемент управления не отображается в диалоговом окне во время тестирования, или же само диалоговое окно не отображается.  
  
 **Пример неполадки**  
  
1.  Создайте проект Win32, измените параметры приложения таким образом, чтобы это было приложение Windows \(а не консольное приложение\).  
  
2.  В [представлении ресурсов](../windows/resource-view-window.md) дважды щелкните RC\-файл.  
  
3.  В группе параметров диалогового окна щелкните поле **О программе**.  
  
4.  Добавьте в диалоговое окно **Элемент управления "IP\-адрес"**.  
  
5.  Щелкните "Сохранить", а затем **Перестроить все**.  
  
6.  Выполните программу.  
  
7.  В меню **Справка** диалогового окна выберите команду **О программе**; диалоговое окно не появится.  
  
 **Причина**  
  
 В настоящий момент редактор диалоговых окон не добавляет автоматически код в проект, если пользователь добавляет общий элемент управления или элемент управления "Rich Edit" в диалоговое окно методом перетаскивания.  Visual Studio в свою очередь не выдает сообщение об ошибке или предупреждение, когда данная ошибка возникает.  Код элемента управления следует добавить вручную.  
  
||||  
|-|-|-|  
|Элемент управления "Ползунок"|Элемент управления "Дерево"|Элемент управления "Выбор даты и времени"|  
|Элемент управления "Счетчик"|Элемент управления "Вкладка"|Элемент управления "Календарь на месяц"|  
|Элемент управления "Индикатор выполнения"|Элемент управления "Анимация"|Элемент управления "IP\-адрес"|  
|Элемент управления "Сочетание клавиш"|Элемент управления "Rich Edit"|Элемент управления "Расширенное поле со списком"|  
|Элемент управления "Список"|Элемент управления "Rich Edit 2.0"|Пользовательский элемент управления|  
  
## Исправление ошибки при добавлении общих элементов управления  
 Чтобы в диалоговом окне можно было использовать общие элементы управления, прежде чем создавать диалоговое окно необходимо вызвать метод [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) или **AFXInitCommonControls**.  
  
## Исправление ошибки при добавлении элементов управления "Rich Edit"  
 Для элементов управления "Rich Edit" необходим вызвать метод **LoadLibrary**.  Дополнительные сведения см. в разделах [Использование элемента управления RichEdit 1.0 с MFC](../Topic/Using%20the%20RichEdit%201.0%20Control%20with%20MFC.md) и [Об элементах управления "Rich Edit"](http://msdn.microsoft.com/library/windows/desktop/bb787873) документации по [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)], а также в [Общих сведениях об элементах управления "Rich Edit"](../mfc/overview-of-the-rich-edit-control.md).  
  
## Требования  
 Win32  
  
## См. также  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)