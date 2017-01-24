---
title: "Создание приложения MFC в стиле веб-браузера | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcweb.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC - библиотека, в веб-приложениях"
  - "в веб-приложениях, создание"
  - "веб-браузеры"
  - "веб-браузеры, создание из архитектуры MFC"
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание приложения MFC в стиле веб-браузера
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Приложение в стиле браузера может получать доступ к информации в Интернете \(такой как HTML\-страницы или активные документы\) или в интрасети, а также в папках локальной файловой системы и сетевых папках.  Сделав класс представления приложения производным от [CHtmlView](../../mfc/reference/chtmlview-class.md), вы фактически превращаете приложение в браузер, создавая представление с элементом управления WebBrowser.  
  
### Создание приложения в стиле браузера на основе архитектуры документ\/представление MFC  
  
1.  Следуйте инструкциям в разделе [Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  На странице [Тип приложения](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) мастера приложений MFC убедитесь, что установлен флажок **Архитектура документ\/представление**. \(Вы можете выбрать **Однодокументное** или **Многодокументное**, но не **Диалоговое**.\)  
  
3.  На странице [Обзор созданных классов](../../mfc/reference/generated-classes-mfc-application-wizard.md) в раскрывающемся меню **Базовый класс** выберите `CHtmlView`.  
  
4.  Установите все остальные параметры, которые необходимы в скелете приложения.  
  
5.  Нажмите кнопку **Готово**.  
  
 Элемент управления WebBrowser поддерживает просмотр веб\-страниц с переходом по гиперссылкам и URL\-адресам.  Элемент управления хранит журнал просмотра, что позволяет пользователю перемещаться вперед и назад по ранее просматривавшимся веб\-узлам, папкам и документам.  Элемент управления непосредственно обрабатывает перемещение, гиперссылки, журнал просмотра, избранное и безопасность.  Приложения могут также использовать элемент управления WebBrowser в качестве контейнера для активных документов.  Это позволит открывать документы со сложным форматированием, например электронные таблицы Microsoft Excel или документы Word, и редактировать их непосредственно из элемента управления WebBrowser.  Элемент управления WebBrowser является также контейнером для элементов управления ActiveX, и в нем можно размещать любой такой элемент.  
  
> [!NOTE]
>  Элемент управления ActiveX WebBrowser \(а следовательно, и `CHtmlView`\) доступен только для приложений, работающих под управлением тех версий операционной системы Windows, в которых установлен браузер Internet Explorer 4.0, и более поздних версий.  
  
 Поскольку `CHtmlView` просто реализует элемент управления браузера корпорации Майкрософт, поддержка печати в нем осуществляется иначе, чем в других классах, производных от [CView](../Topic/CView%20Class.md).  Элемент управления WebBrowser реализует пользовательский интерфейс принтера и печать.  Поэтому `CHtmlView` не поддерживает предварительный просмотр перед печатью, а среда не предоставляет других функций поддержки печати, например [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md), [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md) и [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md), которые доступны в других приложениях MFC.  
  
 `CHtmlView` действует как оболочка для элемента управления браузера, который снабжает приложение представлением веб\- или HTML\-страницы.  Мастер создает переопределение функции [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) в классе представления, предоставляя ссылку для перехода на веб\-узел Microsoft Visual C\+\+:  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),NULL,NULL);  
}  
```  
  
 Вы можете заменить этот узел другим или использовать функцию\-член [LoadFromResource](../Topic/CHtmlView::LoadFromResource.md) для открытия HTML\-страницы, находящейся в скрипте ресурсов проекта в качестве просматриваемого по умолчанию содержимого.  Примеры.  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   LoadFromResource(IDR_HTML1);  
}  
```  
  
## См. также  
 [MFC Sample MFCIE](http://msdn.microsoft.com/ru-ru/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [мастер приложений MFC](../Topic/MFC%20Application%20Wizard.md)   
 [Работа со свойствами проектов](../../ide/working-with-project-properties.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Работа со свойствами проектов](../../ide/working-with-project-properties.md)   
 [Deploying Applications](http://msdn.microsoft.com/ru-ru/4ff8881d-0daf-47e7-bfe7-774c625031b4)