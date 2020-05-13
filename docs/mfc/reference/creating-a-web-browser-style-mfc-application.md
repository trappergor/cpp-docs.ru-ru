---
title: Создание приложения MFC в стиле браузера
ms.date: 06/25/2018
f1_keywords:
- vc.appwiz.mfcweb.project
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
ms.openlocfilehash: e02e928f65ab4cd918e730135abc62ed3237decf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215128"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Создание приложения MFC в стиле браузера

Веб-приложение в стиле браузера может получать доступ к информации из Интернета (например, к HTML или активным документам) или интрасети, а также к папкам в локальной файловой системе и сети. Если класс представления приложения является производным от [CHtmlView](../../mfc/reference/chtmlview-class.md), то фактически вы делаете приложение веб-браузером, предоставляя представление с элементом управления WebBrowser.

## <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>Создание приложения веб-браузера на основе архитектуры "документ-представление MFC"

1. Следуйте инструкциям по [созданию приложения MFC](../../mfc/reference/creating-an-mfc-application.md).

1. На странице [Тип приложения](../../mfc/reference/application-type-mfc-application-wizard.md) мастера приложений MFC убедитесь, что выбрано поле **архитектура документ/представление** . (Можно выбрать **один документ** или **несколько документов**, но не **на основе диалогового окна**.)

1. На странице [Проверка созданных классов](../../mfc/reference/generated-classes-mfc-application-wizard.md) используйте раскрывающееся меню **базовый класс** , чтобы выбрать `CHtmlView`.

1. Выберите любые другие параметры, которые вы хотите встроить в скелет приложения.

1. Нажмите кнопку **Готово**.

Элемент управления WebBrowser поддерживает просмотр веб-страниц через гиперссылки и навигацию по URL-адресу. Элемент управления поддерживает список журналов, позволяющий пользователю просматривать и просматривать ранее просмотренные сайты, папки и документы. Элемент управления непосредственно обрабатывает навигацию, гиперссылки, списки журналов, избранное и безопасность. Приложения могут использовать элемент управления WebBrowser в качестве активного контейнера документа для размещения активных документов. Таким образом, документы с расширенным форматированием, такие как электронные таблицы Microsoft Excel или документы Word, можно открывать и редактировать на месте с помощью элемента управления WebBrowser. Элемент управления WebBrowser также является контейнером элементов управления ActiveX, который может размещать любой элемент управления ActiveX.

> [!NOTE]
> Элемент управления ActiveX WebBrowser (и, следовательно `CHtmlView`) доступен только для приложений, работающих под управлением версий Windows, в которых установлен Internet Explorer 4,0 или более поздней версии.

Поскольку `CHtmlView` просто реализует элемент управления веб-браузера Майкрософт, его поддержка печати не похожа на другие классы, производные от [CView](../../mfc/reference/cview-class.md). Вместо этого элемент управления WebBrowser реализует пользовательский интерфейс принтера и печать. В результате `CHtmlView` не поддерживает предварительный просмотр, а платформа не предоставляет другие функции поддержки печати: например, [CView:: онпрепарепринтинг](../../mfc/reference/cview-class.md#onprepareprinting), [CView:: онбегинпринтинг](../../mfc/reference/cview-class.md#onbeginprinting)и [CView:: онендпринтинг](../../mfc/reference/cview-class.md#onendprinting), которые доступны в других приложениях MFC.

`CHtmlView` выступает в качестве оболочки для элемента управления веб-браузера, который предоставляет приложению представление в виде веб-страницы или HTML. Мастер создает переопределение функции [онинитиалупдате](../../mfc/reference/cview-class.md#oninitialupdate) в классе представления, предоставляя ссылку навигации на веб-сайт Microsoft Visual C++ Web site:

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    Navigate2(_T("http://www.docs.microsoft.com/"),
        NULL,
        NULL);
}
```

Вы можете заменить этот сайт собственным или использовать функцию-член [лоадфромресаурце](../../mfc/reference/chtmlview-class.md#loadfromresource) , чтобы открыть HTML-страницу, которая находится в скрипте ресурсов проекта в качестве содержимого по умолчанию для представления. Пример:

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    LoadFromResource(IDR_HTML1);
}
```

## <a name="see-also"></a>См. также раздел

[Пример MFCIE для MFC](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/internet)<br/>
[Мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md)<br/>
[Настройка компилятора и свойств сборки](../../build/working-with-project-properties.md)<br/>
[Страницы свойств](../../build/reference/property-pages-visual-cpp.md)<br/>
[Настройка компилятора и свойств сборки](../../build/working-with-project-properties.md)
