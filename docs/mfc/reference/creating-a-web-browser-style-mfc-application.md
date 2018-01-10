---
title: "Создание приложения MFC в стиле браузера веб | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfcweb.project
dev_langs: C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7b886f2f1eeed327c2f07f1776777771a5d6ad6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Создание приложения MFC в стиле браузера
Веб-приложении обозревателя доступны сведения из Интернета (например, HTML или активные документы) или интрасети, а также папки в локальной файловой системе и в сети. Путем создания производного класса представления приложения из [CHtmlView](../../mfc/reference/chtmlview-class.md), эффективно сделать приложение веб-браузер, создавая представление с элементом управления WebBrowser.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>Создание приложения веб-браузера на основе архитектуры документ/представление MFC  
  
1.  Следуйте указаниям, приведенным в [Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  В мастере приложений MFC [тип приложения](../../mfc/reference/application-type-mfc-application-wizard.md) страницы, убедитесь, что **архитектуры Document/view** флажок. (Вы также можете выбрать **однооконный** или **несколько документов**, но не **на базе диалогового окна**.)  
  
3.  На [обзор созданных классов](../../mfc/reference/generated-classes-mfc-application-wizard.md) используйте **базового класса** раскрывающееся меню для выбора `CHtmlView`.  
  
4.  Выберите любые другие нужные параметры встроены в общую схему приложения.  
  
5.  Нажмите кнопку **Готово**.  
  
 Элемент управления WebBrowser поддерживает просмотр веб-страниц по гиперссылкам и навигации унифицированный указатель ресурса (URL). Элемент управления поддерживает список журнала, который позволяет пользователю перемещаться вперед и назад по ранее просмотренных сайты, папки и документы. Элемент управления непосредственно обрабатывает навигации, гиперссылки, списки журнала, избранного и безопасности. Приложения могут использовать элемент управления WebBrowser в качестве контейнер активных документов для активных документов также. Таким образом документы со сложным форматированием, например электронные таблицы Microsoft Excel или документ Word можно открыть и редактировать непосредственно из элемента управления WebBrowser. Элемент управления WebBrowser — также контейнеров элементов управления ActiveX, который может содержать любой элемент управления ActiveX.  
  
> [!NOTE]
>  Элемент управления WebBrowser ActiveX (и, следовательно, `CHtmlView`) доступен только для приложений под управлением версий Windows, в которой Internet Explorer 4.0 или более поздней версии была установлена.  
  
 Поскольку `CHtmlView` просто реализует элемент управления браузера Microsoft Web, поддерживаются ли для печати не как другой [CView](../../mfc/reference/cview-class.md)-производные классы. Вместо этого элемент управления WebBrowser реализует пользовательский интерфейс принтера и печати. В результате `CHtmlView` does не поддерживает предварительный просмотр и платформа не предоставляет функции для поддержки других печати: например, [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), и [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), они доступны в других приложениях MFC.  
  
 `CHtmlView`действует как оболочка для элемента управления браузера, который снабжает приложение представлением веб- или HTML-страницы. Мастер создает переопределение, чтобы [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) функции в классе представления, предоставляя ссылку навигации для Microsoft Visual C++, веб-сайт:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
    NULL,
    NULL);

} 
```  
  
 Вы можете заменить этот узел, или можно использовать [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) функции-члена для открытия страницы HTML, находящейся в скрипте ресурсов проекта в качестве содержимого по умолчанию для представления. Пример:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    LoadFromResource(IDR_HTML1);

} 
```  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [Мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md)   
 [Работа со свойствами проектов](../../ide/working-with-project-properties.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Работа со свойствами проектов](../../ide/working-with-project-properties.md)   
 [Развертывание приложений](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

