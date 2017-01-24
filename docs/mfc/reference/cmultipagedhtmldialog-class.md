---
title: "CMultiPageDHtmlDialog Class | Microsoft Docs"
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
  - "CMultiPageDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPageDHtmlDialog class"
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiPageDHtmlDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Многостраничных диалоговое окно отображает несколько страниц HTML последовательно и обрабатываются события из каждой страницы.  
  
## Синтаксис  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog.md)|Создание многостраничных объект диалогового окна мастер\- стиля \(DHTML\).|  
|[CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog.md)|Уничтожает многостраничных объект диалоговое окно DHTML.|  
  
## Заметки  
 Механизм, позволяющий сделать это [Сопоставление событий DHTML и url\-адреса](http://msdn.microsoft.com/ru-ru/2a7332f0-79d7-46e4-b816-0a618c46777a), содержащее [внедренные сопоставления события](../Topic/BEGIN_EMBED_DHTML_EVENT_MAP.md) для каждой страницы.  
  
## Пример  
 Это многостраничных диалоговое окно занимает 3 ресурсов HTML, определяющие простое мастер\- как функциональные возможности.  Первая страница имеет кнопку `Next`, вторая кнопка **Назад** и `Next`, а третий \- кнопку **Назад**.  При нажатии одной из кнопок, вызовы функций [CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md) обработчика для загрузки соответствующей новой странице.  
  
 Соответствующие части объявления класса \(в CMyMultiPageDlg.h\):  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_1.h)]  
  
 Соответствующие части реализации класса \(в CMyMultipageDlg.cpp\):  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../Topic/CDHtmlDialog%20Class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## Требования  
 **Header:** afxdhtml.h  
  
## См. также  
 [CDHtmlDialog Class](../Topic/CDHtmlDialog%20Class.md)   
 [Multipage DHTML and URL Event Maps \(NIB\)](http://msdn.microsoft.com/ru-ru/2a7332f0-79d7-46e4-b816-0a618c46777a)