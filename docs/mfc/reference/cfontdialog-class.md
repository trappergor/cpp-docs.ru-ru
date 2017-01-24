---
title: "CFontDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFontDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontDialog class"
  - "диалоговые окна, шрифты"
  - "шрифты"
  - "шрифты, выбор"
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFontDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет включить диалоговое окно шрифт\- выделения в приложение.  
  
## Синтаксис  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFontDialog::CFontDialog](../Topic/CFontDialog::CFontDialog.md)|Создает объект `CFontDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFontDialog::DoModal](../Topic/CFontDialog::DoModal.md)|Отображает диалоговое окно и позволяет пользователю выполнить выделение.|  
|[CFontDialog::GetCharFormat](../Topic/CFontDialog::GetCharFormat.md)|Извлекает форматирования символов выбранного шрифта.|  
|[CFontDialog::GetColor](../Topic/CFontDialog::GetColor.md)|Возвращает цвет выбранного шрифта.|  
|[CFontDialog::GetCurrentFont](../Topic/CFontDialog::GetCurrentFont.md)|Присвоит характеристики выбранного в данный момент шрифта в структуре `LOGFONT`.|  
|[CFontDialog::GetFaceName](../Topic/CFontDialog::GetFaceName.md)|Возвращает имя шрифта, выбранного шрифта.|  
|[CFontDialog::GetSize](../Topic/CFontDialog::GetSize.md)|Возвращает размер точки выбранного шрифта.|  
|[CFontDialog::GetStyleName](../Topic/CFontDialog::GetStyleName.md)|Возвращает имя стиля выбранного шрифта.|  
|[CFontDialog::GetWeight](../Topic/CFontDialog::GetWeight.md)|Возвращает вес выбранного шрифта.|  
|[CFontDialog::IsBold](../Topic/CFontDialog::IsBold.md)|Определяет, является ли шрифт полужирным.|  
|[CFontDialog::IsItalic](../Topic/CFontDialog::IsItalic.md)|Определяет, является ли шрифт курсивом.|  
|[CFontDialog::IsStrikeOut](../Topic/CFontDialog::IsStrikeOut.md)|Указывает, отображается ли шрифт с аутом.|  
|[CFontDialog::IsUnderline](../Topic/CFontDialog::IsUnderline.md)|Подчеркивание указывает, является ли шрифт.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CFontDialog::m\_cf](../Topic/CFontDialog::m_cf.md)|Структура, используемая для настройки объект `CFontDialog`.|  
  
## Заметки  
 Объект `CFontDialog` диалоговое окно со списком шрифтов, которые в настоящее время установлены в системе.  Пользователь может выбрать указанный шрифт из списка, и это выделение затем передается обратно приложению.  
  
 Создание объекта `CFontDialog`, использовать предоставленный конструктор или создать новый подкласс и использовать собственный пользовательский конструктор.  
  
 Как только объект `CFontDialog` построен, можно использовать структуру `m_cf` для инициализации значений или состояния элементов управления в диалоговом окне.  Структура [m\_cf](../Topic/CFontDialog::m_cf.md) типа [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832).  Дополнительные сведения об этой структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 После инициализации управления диалогового окна, вызовите функцию\-член объекта `DoModal` для отображения диалогового окна и, чтобы разрешить пользователю выбирать шрифт.  Возвращает `DoModal` выбрал ли пользователь кнопку ОК \(**IDOK**\) или Отмены \(**IDCANCEL**\).  
  
 Если `DoModal` возвращает **IDOK**, можно использовать один из `CFontDialog` функции\-члены для получения ввода информации пользователем.  
  
 Можно использовать функцию Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) чтобы определить, произошла ли ошибка во время инициализации диалогового окна и получить дополнительные сведения об ошибке.  Дополнительные сведения об этой функции см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CFontDialog` основан на файле COMMDLG.DLL, который поставляется с версиями Windows 3,1 и более поздних версий.  
  
 Настраивать диалоговое окно, наследуйте класс от `CFontDialog` укажите пользовательский шаблон диалогового окна, и добавьте сообщение\- сопоставление для обработки сообщений уведомлений от расширенных элементов управления.  Все необработанных сообщений должны быть переданы на базовый класс.  
  
 Функция обработчика настройке не требуется.  
  
 Дополнительные сведения об использовании `CFontDialog` см. в разделе [Общие классы диалоговых окон](../../mfc/common-dialog-classes.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CFontDialog`  
  
## Требования  
 **Header:**  afxdlgs.h  
  
## См. также  
 [MFC просматривает HIERSVR](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../Topic/CCommonDialog%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)