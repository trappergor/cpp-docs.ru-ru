---
title: "Создание приложения MFC в стиле браузера веб | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications, creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ccfb093a65c3f9a72b6180c4f415a92ebaf18684
ms.lasthandoff: 02/24/2017

---
# <a name="creating-a-web-browser-style-mfc-application"></a>Создание приложения MFC в стиле браузера
Веб-приложение стиле браузера доступны сведения из Интернета (например, HTML или активные документы) или интрасети, а также папки в локальной файловой системы и сети. Путем создания производного класса представления приложения от [CHtmlView](../../mfc/reference/chtmlview-class.md), фактически сделать приложение веб-обозреватель, создавая представление с элементом управления WebBrowser.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>Создание приложения веб-браузера на основе архитектуры документ/представление MFC  
  
1.  Следуйте указаниям, приведенным в [Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  В мастере приложений MFC [тип приложения](../../mfc/reference/application-type-mfc-application-wizard.md) страницы, убедитесь, что **архитектуры документ/представление** установлен. (Можно выбрать либо **одного документа** или **нескольких документов**, но не **на базе диалогового окна**.)  
  
3.  На [обзор созданных классов](../../mfc/reference/generated-classes-mfc-application-wizard.md) используйте **базового класса** раскрывающееся меню для выбора `CHtmlView`.  
  
4.  Выберите любые другие нужные параметры встроенные в общую схему приложения.  
  
5.  Нажмите кнопку **Готово**.  
  
 Элемент управления WebBrowser поддерживает просмотр по гиперссылкам и навигации унифицированный указатель ресурса (URL). Элемент управления сохраняет список журнала, который позволяет пользователю перемещаться вперед и назад по ранее просмотренных узлов, папок и документов. Элемент управления непосредственно обрабатывает навигации, гиперссылки, списки журнала, избранного и безопасности. Приложения могут использовать элемент управления WebBrowser как контейнер активного документа для активных документов также. Таким образом документы со сложным форматированием, например электронные таблицы Microsoft Excel или документ Word можно открывать и изменять непосредственно из элемента управления WebBrowser. Элемент управления WebBrowser является также контейнера элементов управления ActiveX, который может содержать любой элемент управления ActiveX.  
  
> [!NOTE]
>  Элемент управления WebBrowser ActiveX (и, следовательно, `CHtmlView`) доступна только для приложений под управлением версий Windows, в которой Internet Explorer 4.0 или более поздней версии была установлена.  
  
 Поскольку `CHtmlView` просто реализует управления браузера корпорации Майкрософт, поддержка печати не имеет, как [CView](../../mfc/reference/cview-class.md)-производные классы. Вместо этого элемент управления WebBrowser реализует пользовательский интерфейс принтера и печати. В результате `CHtmlView` does не поддерживает режим предварительного просмотра, и платформа не предоставляет другие функции для поддержки печати: например, [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), и [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), которые доступны в других приложениях MFC.  
  
 `CHtmlView`действует как оболочка для элемента управления браузера, который снабжает приложение представлением веб- или HTML-страницы. Мастер создает переопределение, чтобы [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) функция в классе представления навигации ссылку на Microsoft Visual C++, веб-сайта:  
  
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
 [Работа со свойствами проекта](../../ide/working-with-project-properties.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Работа со свойствами проекта](../../ide/working-with-project-properties.md)   
 [Развертывание приложений](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)


