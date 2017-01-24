---
title: "CMFCKeyMapDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCKeyMapDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCKeyMapDialog class"
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCKeyMapDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCKeyMapDialog` поддерживает элемент управления, который сопоставляет команды к ключам на клавиатуре.  
  
## Синтаксис  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](../Topic/CMFCKeyMapDialog::CMFCKeyMapDialog.md)|Создает объект `CMFCKeyMapDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCKeyMapDialog::DoModal](../Topic/CMFCKeyMapDialog::DoModal.md)|Отображает диалоговое окно сопоставления клавиатуры.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCKeyMapDialog::FormatItem](../Topic/CMFCKeyMapDialog::FormatItem.md)|Вызываемый платформой для построения строку, описывающую ключевое сопоставление.  По умолчанию строка содержит имя команды, используемых сочетаний клавиш и описание сочетания клавиш.|  
|[CMFCKeyMapDialog::GetCommandKeys](../Topic/CMFCKeyMapDialog::GetCommandKeys.md)|Извлекает строку, содержащую список сочетаний клавиш, связанных с указанной командой.|  
|[CMFCKeyMapDialog::OnInsertItem](../Topic/CMFCKeyMapDialog::OnInsertItem.md)|Вызывается инфраструктурой перед добавлением нового элемента в элемент управления внутренний Список, который поддерживает управление сопоставления клавиатуры.|  
|[CMFCKeyMapDialog::OnPrintHeader](../Topic/CMFCKeyMapDialog::OnPrintHeader.md)|Вызываемый платформой, чтобы напечатать заголовок для сопоставления с клавиатуры на новой странице.|  
|[CMFCKeyMapDialog::OnPrintItem](../Topic/CMFCKeyMapDialog::OnPrintItem.md)|Вызываемый платформой для печати элемент сопоставления клавиатуры.|  
|[CMFCKeyMapDialog::OnSetColumns](../Topic/CMFCKeyMapDialog::OnSetColumns.md)|Вызываемый платформой для задания заголовки столбцов во внутреннем элементе управления "Список", который поддерживает управление сопоставления клавиатуры.|  
|[CMFCKeyMapDialog::PrintKeyMap](../Topic/CMFCKeyMapDialog::PrintKeyMap.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Печать**.|  
|[CMFCKeyMapDialog::SetColumnsWidth](../Topic/CMFCKeyMapDialog::SetColumnsWidth.md)|Вызываемый платформой для задания ширины столбцов во внутреннем элементе управления "Список", который поддерживает управление сопоставления клавиатуры.|  
  
## Заметки  
 Используйте класс `CMFCKeyMapDialog` для реализации изменяемого размера диалогового окна сопоставления клавиатуры.  Диалоговое окно " использует элементе управления списка для отображения сочетаний клавиш и связанных с ними команд.  
  
 Для использования класса `CMFCKeyMapDialog` в приложении, передайте указатель к главному фреймовому окно в качестве параметра конструктору `CMFCKeyMapDialog`.  Затем вызовите метод `DoModal` для запуска модальное диалоговое окно.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## Требования  
 **заголовок:** afxkeymapdialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)