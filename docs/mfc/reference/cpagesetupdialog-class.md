---
title: "CPageSetupDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPageSetupDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPageSetupDialog class"
  - "OLE Page Setup dialog box"
  - "параметры страницы"
  - "Параметры страницы - диалоговое окно"
  - "Print Setup dialog box"
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CPageSetupDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует службы, предоставленные диалоговом окне параметры страницы Windows общим OLE с дополнительной поддержки для параметра и изменение поля печати.  
  
## Синтаксис  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPageSetupDialog::CPageSetupDialog](../Topic/CPageSetupDialog::CPageSetupDialog.md)|Создает объект `CPageSetupDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPageSetupDialog::CreatePrinterDC](../Topic/CPageSetupDialog::CreatePrinterDC.md)|Создает контекст устройства печати.|  
|[CPageSetupDialog::DoModal](../Topic/CPageSetupDialog::DoModal.md)|Отображает диалоговое окно, и позволяет пользователю выполнить выделение.|  
|[CPageSetupDialog::GetDeviceName](../Topic/CPageSetupDialog::GetDeviceName.md)|Возвращает имя устройства принтера.|  
|[CPageSetupDialog::GetDevMode](../Topic/CPageSetupDialog::GetDevMode.md)|Возвращает текущее `DEVMODE` принтера.|  
|[CPageSetupDialog::GetDriverName](../Topic/CPageSetupDialog::GetDriverName.md)|Возвращает драйвер, используемый принтером.|  
|[CPageSetupDialog::GetMargins](../Topic/CPageSetupDialog::GetMargins.md)|Возвращает параметры области текущего элемента принтера.|  
|[CPageSetupDialog::GetPaperSize](../Topic/CPageSetupDialog::GetPaperSize.md)|Возвращает размер бумаги принтера.|  
|[CPageSetupDialog::GetPortName](../Topic/CPageSetupDialog::GetPortName.md)|Возвращает имя порта вывода.|  
|[CPageSetupDialog::OnDrawPage](../Topic/CPageSetupDialog::OnDrawPage.md)|Вызываемый платформой для обработки экранное изображение выводимой на печать страницы.|  
|[CPageSetupDialog::PreDrawPage](../Topic/CPageSetupDialog::PreDrawPage.md)|Вызывается инфраструктурой перед отрисовкой изображения экранное выводимой на печать страницы.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPageSetupDialog::m\_psd](../Topic/CPageSetupDialog::m_psd.md)|Структура, используемая для настройки объект `CPageSetupDialog`.|  
  
## Заметки  
 Этот класс предназначен для принятия размещение диалогового окна настройки печати.  
  
 Чтобы использовать объект `CPageSetupDialog`, сначала создайте объект с помощью конструктора `CPageSetupDialog`.  Как только было создано диалоговое окно можно задавать или изменять все значения в элементе данных `m_psd` для инициализации значений элементов управления диалогового окна.  Структура [m\_psd](../Topic/CPageSetupDialog::m_psd.md) типа **PAGESETUPDLG**.  
  
 После инициализации элементов управления диалогового окна, вызовите функцию\-член `DoModal` для отображения диалогового окна и, чтобы разрешить пользователю выбирать параметры печати.  Возвращает `DoModal` выбрал ли пользователь кнопку ОК \(**IDOK**\) или Отмены \(**IDCANCEL**\).  
  
 Если `DoModal` возвращает **IDOK**, можно использовать несколько функций элементов `CPageSetupDialog` или доступ к элементу данных `m_psd` для получения ввода информации пользователем.  
  
> [!NOTE]
>  После того как общее OLE диалоговое окно "параметры страницы" будет закрыто все изменения, выполненные пользователем, не будут сохранены границами.  Оно само приложение должно сохранять все значения из этого диалогового окна в постоянном расположении, как элемент документа приложения или класса приложения.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CPageSetupDialog`  
  
## Требования  
 **Header:**  afxdlgs.h  
  
## См. также  
 [Образец WORDPAD MFC](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../Topic/CCommonDialog%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)