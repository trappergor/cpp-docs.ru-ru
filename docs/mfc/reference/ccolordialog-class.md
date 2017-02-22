---
title: "CColorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColorDialog class"
  - "colors, диалоговое окно"
  - "диалоговые окна, colors"
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет включить диалоговое окно цвет\- выделения в приложение.  
  
## Синтаксис  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CColorDialog::CColorDialog](../Topic/CColorDialog::CColorDialog.md)|Создает объект `CColorDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CColorDialog::DoModal](../Topic/CColorDialog::DoModal.md)|Отображает диалоговое окно цвет, и позволяет пользователю выполнить выделение.|  
|[CColorDialog::GetColor](../Topic/CColorDialog::GetColor.md)|Возвращает структуру **COLORREF**, содержащий значения выбранного цвета.|  
|[CColorDialog::GetSavedCustomColors](../Topic/CColorDialog::GetSavedCustomColors.md)|Получает цвет, созданные пользователем.|  
|[CColorDialog::SetCurrentColor](../Topic/CColorDialog::SetCurrentColor.md)|Проверяет текущее выделение цвета в указанный цвет.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CColorDialog::OnColorOK](../Topic/CColorDialog::OnColorOK.md)|Переопределение для проверки цвета, введенный в диалоговое окно.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CColorDialog::m\_cc](../Topic/CColorDialog::m_cc.md)|Структура, используемая для настройки параметры диалогового окна.|  
  
## Заметки  
 Объект `CColorDialog` диалоговое окно со списком цветов, которые определены для отображения системных.  Пользователь может выбрать или создать указанный основной цвет из списка, затем обратно к приложению, когда отображается диалоговое окно будет.  
  
 Создание объекта `CColorDialog`, использовать предоставленный конструктор или наследовать новый класс и использовать собственный пользовательский конструктор.  
  
 Как только было создано диалоговое окно можно задавать или изменять все значения в структуре [m\_cc](../Topic/CColorDialog::m_cc.md) для инициализации значений элементов управления диалогового окна.  Структура `m_cc` типа [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 После инициализации элементов управления диалогового окна, вызовите функцию\-член `DoModal` для отображения диалогового окна и, чтобы разрешить пользователю выбирать цвета.  Возвращает `DoModal` выделения пользователя или диалогового окна ОДОБРЕННОГО \(**IDOK**\) или кнопку "Отмена" \(**IDCANCEL**\).  
  
 Если `DoModal` возвращает **IDOK**, можно использовать один из `CColorDialog` функции\-члены для получения ввода информации пользователем.  
  
 Можно использовать функцию Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) чтобы определить, произошла ли ошибка во время инициализации диалогового окна и получить дополнительные сведения об ошибке.  
  
 `CColorDialog` основан на файле COMMDLG.DLL, который поставляется с версиями Windows 3,1 и более поздних версий.  
  
 Настраивать диалоговое окно создать класс, производный от `CColorDialog`, предоставить пользовательский шаблон диалогового окна, и добавить сопоставление сообщений для обработки сообщений уведомлений от расширенных элементов управления.  Все необработанных сообщений должны быть переданы на базовый класс.  
  
 Функция обработчика настройке не требуется.  
  
> [!NOTE]
>  На некоторых типах установки объект `CColorDialog` не отображают с серым фоном при использовании границы, чтобы сделать другой серый цвет объектов `CDialog`.  
  
 Дополнительные сведения об использовании `CColorDialog` см. в разделе [Общие классы диалоговых окон](../../mfc/common-dialog-classes.md)  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CColorDialog`  
  
## Требования  
 **Header:**  afxdlgs.h  
  
## См. также  
 [MFC, пытается интерфейс MDI](../../top/visual-cpp-samples.md)   
 [Образец DRAWCLI MFC](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../Topic/CCommonDialog%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)