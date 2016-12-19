---
title: "CPrintDialogEx Class | Microsoft Docs"
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
  - "CPrintDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialogEx class"
  - "Печать - диалоговое окно"
  - "Print Setup dialog box"
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrintDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует службы, предоставленные страницей свойств печати в Windows 2000.  
  
## Синтаксис  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPrintDialogEx::CPrintDialogEx](../Topic/CPrintDialogEx::CPrintDialogEx.md)|Создает объект `CPrintDialogEx`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPrintDialogEx::CreatePrinterDC](../Topic/CPrintDialogEx::CreatePrinterDC.md)|Создает контекст устройства принтере без отображения диалогового окна печати.|  
|[CPrintDialogEx::DoModal](../Topic/CPrintDialogEx::DoModal.md)|Отображает диалоговое окно и позволяет пользователю выполнить выделения.|  
|[CPrintDialogEx::GetCopies](../Topic/CPrintDialogEx::GetCopies.md)|Возвращает запрошенное число копий.|  
|[CPrintDialogEx::GetDefaults](../Topic/CPrintDialogEx::GetDefaults.md)|Получает устройство по умолчанию без отображения диалогового окна.|  
|[CPrintDialogEx::GetDeviceName](../Topic/CPrintDialogEx::GetDeviceName.md)|Извлекает имя выбранного в данный момент устройства принтера.|  
|[CPrintDialogEx::GetDevMode](../Topic/CPrintDialogEx::GetDevMode.md)|Извлекает структуру `DEVMODE`.|  
|[CPrintDialogEx::GetDriverName](../Topic/CPrintDialogEx::GetDriverName.md)|Извлекает имя система\- заданного драйвера устройства принтера.|  
|[CPrintDialogEx::GetPortName](../Topic/CPrintDialogEx::GetPortName.md)|Извлекает имя выбранного в данный момент порта принтера.|  
|[CPrintDialogEx::GetPrinterDC](../Topic/CPrintDialogEx::GetPrinterDC.md)|Получает дескриптор контекста устройства принтера.|  
|[CPrintDialogEx::PrintAll](../Topic/CPrintDialogEx::PrintAll.md)|Указывает, нужно ли выводить все страницы документа.|  
|[CPrintDialogEx::PrintCollate](../Topic/CPrintDialogEx::PrintCollate.md)|Определяет, является ли разбирается по копиям копии.|  
|[CPrintDialogEx::PrintCurrentPage](../Topic/CPrintDialogEx::PrintCurrentPage.md)|Определяет, является ли печать текущей страницы документа.|  
|[CPrintDialogEx::PrintRange](../Topic/CPrintDialogEx::PrintRange.md)|Указывает, нужно ли выводить только заданный диапазон страниц.|  
|[CPrintDialogEx::PrintSelection](../Topic/CPrintDialogEx::PrintSelection.md)|Указывает, нужно ли выводить только в данный момент выбранные элементы.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPrintDialogEx::m\_pdex](../Topic/CPrintDialogEx::m_pdex.md)|Структура, используемая для настройки объект `CPrintDialogEx`.|  
  
## Заметки  
 Можно положиться на платформе, чтобы обрабатывать многие аспекты процесса печати для приложения.  Дополнительные сведения об использовании платформы для обработки задачи печати см. в статье [Печать](../../mfc/printing.md).  
  
 Если необходимо приложению обрабатывать печать без вмешательства платформ, то можно использовать класс `CPrintDialogEx` "как" с использованием предоставленного конструктору или можно создать собственный класс из диалогового окна конструктор `CPrintDialogEx` и записи в соответствии с свои мере необходимости.  В любом случае эти диалоговые окна будут вести себя как стандартные диалоговые окна MFC, поскольку они наследуются от класса `CCommonDialog`.  
  
 Чтобы использовать объект `CPrintDialogEx`, сначала создайте объект с помощью конструктора `CPrintDialogEx`.  Как только было создано диалоговое окно можно задавать или изменять все значения в структуре [m\_pdex](../Topic/CPrintDialogEx::m_pdex.md) для инициализации значений элементов управления диалогового окна.  Структура `m_pdex` типа [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844).  Дополнительные сведения об этой структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Если не предоставить собственные маркеры для элементов в `m_pdex`**hDevMode** и **hDevNames**, необходимо вызвать функцию Windows **GlobalFree** для этих маркеров после завершения с диалоговым окном.  
  
 После инициализации элементов управления диалогового окна, вызовите функцию\-член `DoModal` для отображения диалогового окна и, чтобы разрешить пользователю выбирать параметры печати.  При `DoModal` возвращает можно указать выбрал ли пользователь применяет ОК или отменить.  
  
 Если пользователь отжал кнопку "ОК", то можно использовать функции\-члены `CPrintDialogEx` для получения ввода информации пользователем.  
  
 Функция\-член `CPrintDialogEx::GetDefaults` позволяет извлечь текущие значения по умолчанию принтер без отображения диалогового окна.  Этот метод не требует взаимодействия с пользователем.  
  
 Можно использовать функцию Windows **CommDlgExtendedError** чтобы определить, произошла ли ошибка во время инициализации диалогового окна и получить дополнительные сведения об ошибке.  Дополнительные сведения об этой функции см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения об использовании `CPrintDialogEx` см. в разделе [Общие классы диалоговых окон](../../mfc/common-dialog-classes.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CPrintDialogEx`  
  
## Требования  
 **Header:**  afxdlgs.h  
  
## См. также  
 [CCommonDialog Class](../Topic/CCommonDialog%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Structure](../../mfc/reference/cprintinfo-structure.md)