---
title: 'TN041: MFC-OLE1 Migration to MFC-OLE 2'
ms.date: 10/18/2018
helpviewer_keywords:
- OLE1 [MFC]
- migrating OLE1 to OLE2
- migration [MFC], OLE1 to OLE2
- OLE2 [MFC]
- porting OLE1 to OLE2
- converting OLE1 to OLE2
- upgrading Visual C++ applications [MFC], OLE1 to OLE2
- TN041
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
ms.openlocfilehash: 7d0381983481278b1410ae0ff11463519d4cbb34
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743156"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041. Миграция MFC/OLE1 на MFC/OLE 2

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

## <a name="general-issues-relating-to-migration"></a>Общие проблемы, связанные с миграцией

Одной из целей проектирования классов OLE 2 в MFC 2,5 (и более поздних версиях) было необходимость хранить большую часть той же архитектуры, что и в MFC 2,0 для поддержки OLE 1,0. В результате многие из тех же классов OLE в MFC 2,0 по-прежнему существуют в этой версии MFC ( `COleDocument` ,, `COleServerDoc` `COleClientItem` , `COleServerItem` ). Кроме того, многие API в этих классах идентичны. Тем не менее, OLE 2 значительно отличается от OLE 1,0, поэтому можно рассчитывать, что некоторые детали были изменены. Если вы знакомы с поддержкой OLE1 в MFC 2.0, вы можете работать дома с поддержкой MFC 2,0.

Если вы принимаете существующее приложение MFC или OLE1 и добавляете к нему функции OLE 2, то сначала прочитайте эту заметку. В этом заметке рассматриваются некоторые общие проблемы, которые могут возникнуть при переносе функциональных возможностей OLE1 в MFC/OLE 2, а затем обсуждаются проблемы, обнаруженные при переносе двух приложений, входящих в MFC 2,0: примеры MFC OLE для проектов [OCLIENT](../overview/visual-cpp-samples.md) и [HIERSVR](../overview/visual-cpp-samples.md).

## <a name="mfc-documentview-architecture-is-important"></a>Важность архитектуры документов и представлений MFC

Если приложение не использует архитектуру документов и представлений MFC и вы хотите добавить поддержку OLE 2 в приложение, теперь пора перейти в документ или представление. Многие преимущества классов OLE 2 MFC реализованы только после того, как приложение использует встроенную архитектуру и компоненты MFC.

Реализация сервера или контейнера без использования архитектуры MFC возможна, но не рекомендуется.

## <a name="use-mfc-implementation-instead-of-your-own"></a>Используйте реализацию MFC вместо собственных

Классы с заданной реализацией MFC, такие как `CToolBar` , `CStatusBar` и, `CScrollView` имеют встроенный код специального варианта для поддержки OLE 2. Таким образом, если вы можете использовать эти классы в своем приложении, вы получите преимущества от усилий, чтобы сделать их совместимыми с OLE. Опять же, здесь можно «самостоятельное» классы для этих целей, но это не рекомендуется. Если необходимо реализовать аналогичные функции, исходный код MFC является прекрасным справочником по работе с некоторыми более тонкими точками OLE (особенно когда дело доходит до активации на месте).

## <a name="examine-the-mfc-sample-code"></a>Изучение примера кода MFC

Существует ряд примеров MFC, включающих функции OLE. Каждое из этих приложений реализует OLE по другому расуглу:

- [HIERSVR](../overview/visual-cpp-samples.md) Предназначен главным образом для использования в качестве серверного приложения. Он был включен в MFC 2,0 как приложение MFC или OLE1 и был перенесен в MFC/OLE 2, а затем расширен таким образом, что он реализует множество функций OLE, доступных в OLE 2.

- [OCLIENT](../overview/visual-cpp-samples.md) Это изолированное приложение-контейнер, предназначенное для демонстрации многих функций OLE с точки зрения контейнера. Оно также было перенесено из MFC 2,0, а затем расширено для поддержки многих более сложных функций OLE, таких как пользовательские форматы буфера обмена и ссылки на внедренные элементы.

- [DRAWCLI](../overview/visual-cpp-samples.md) Это приложение реализует поддержку контейнеров OLE во многом подобно OCLIENT, за исключением того, что оно делает это в пределах платформы существующей объектно-ориентированной программы рисования. Здесь показано, как можно реализовать поддержку контейнеров OLE и интегрировать ее в существующее приложение.

- [SUPERPAD](../overview/visual-cpp-samples.md) Это приложение, а также как и автономное приложение, также является сервером OLE. Серверная поддержка, реализованная в ИТ, является крайне минимальной. Особенно интересно, как она использует службы OLE Clipboard для копирования данных в буфер обмена, но использует встроенные функции элемента управления Windows "Правка" для реализации функции вставки буфера обмена. Здесь показано интересное сочетание традиционного использования API Windows, а также интеграция с новыми API-интерфейсами OLE.

Дополнительные сведения о примерах приложений см. в разделе "образец справки MFC".

## <a name="case-study-oclient-from-mfc-20"></a>Пример использования: OCLIENT из MFC 2,0

Как упоминалось выше, [OCLIENT](../overview/visual-cpp-samples.md) включалось в MFC 2,0 и реализовали OLE с MFC/OLE1. Ниже описаны действия, с помощью которых приложение было первоначально преобразовано для использования классов MFC/OLE 2. После завершения первоначального порта было добавлено несколько компонентов, чтобы лучше продемонстрировать классы MFC/OLE. Эти функции не будут рассматриваться здесь. Дополнительные сведения об этих дополнительных возможностях см. в этом образце.

> [!NOTE]
> Ошибки и пошаговые процессы компилятора были созданы с Visual C++ 2,0. Конкретные сообщения об ошибках и расположения могли быть изменены с Visual C++ 4,0, но концептуальные сведения остаются действительными.

### <a name="getting-it-up-and-running"></a>Подготовка и запуск

Подход, выполняемый для переноса примера OCLIENT в MFC/OLE, заключается в том, чтобы начать с его сборки и исправить очевидные ошибки компилятора, которые могут возникнуть. Если сделать пример OCLIENT из MFC 2,0 и скомпилировать его в этой версии MFC, вы обнаружите, что не так много ошибок устранить. Ошибки в порядке их возникновения описаны ниже.

### <a name="compile-and-fix-errors"></a>Компиляция и исправление ошибок

```Output
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters
```

Первая ошибка `COleClientItem::Draw` . В MFC/OLE1 она заняла больше параметров, чем делает версия MFC/OLE. Дополнительные параметры часто не требуются и обычно имеют значение NULL (как в этом примере). Эта версия MFC может автоматически определять значения для Лпвбаундс, когда CDC, в которой выполняется прорисовка, является КОНТРОЛЛЕРом-метафайлом. Кроме того, параметр Пформатдк больше не нужен, так как платформа создаст ее из "атрибута DC" переданного контроллера домена. Чтобы устранить эту проблему, просто удалите два дополнительных параметра NULL для вызова Draw.

```Output
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier
\oclient\mainview.cpp(273) : error C2057: expected constant expression
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
```

Приведенные выше ошибки вызваны тем, что все `COleClientItem::CreateXXXX` функции в MFC/OLE1 требуют передачи уникального имени для представления элемента. Это было требованием к базовому API OLE. Это необязательно в MFC/OLE 2, так как OLE 2 не использует DDE в качестве базового механизма связи (имя было использовано в диалогах DDE). Чтобы устранить эту проблему, можно удалить функцию, а `CreateNewName` также все ссылки на нее. Определить, какая функция MFC/OLE ожидается в этой версии, легко, просто поместив курсор на вызов и нажав клавишу F1.

Еще одна область, значительно отличающаяся, — обработка буфера обмена OLE 2. С помощью OLE1 вы использовали API буфера обмена Windows для взаимодействия с буфером обмена. В случае с OLE 2 это делается с помощью другого механизма. В API MFC/OLE1 предполагается, что буфер обмена был открыт перед копированием `COleClientItem` объекта в буфер обмена. Это больше не требуется и приведет к сбою всех операций в буфере обмена MFC/OLE. При редактировании кода для удаления зависимостей от `CreateNewName` необходимо также удалить код, который открывается и закрывает буфер обмена Windows.

```Output
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function
\oclient\mainview.cpp(344) : error C2057: expected constant expression
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'
```

Эти ошибки возникают из `CMainView::OnInsertObject` обработчика. Обработка команды "вставить новый объект" является еще одной областью, где все изменилось довольно немного. В этом случае проще всего просто выполнить слияние исходной реализации с, предоставляемой помощью мастера, для нового приложения-контейнера OLE. На самом деле, это метод, который можно применять для переноса других приложений. В MFC/OLE1 вы выводите диалоговое окно "Вставка объекта" путем вызова `AfxOleInsertDialog` функции. В этой версии создается `COleInsertObject` объект диалогового окна и вызывается метод `DoModal` . Кроме того, новые элементы OLE создаются с помощью **идентификатора CLSID** , а не строки classname. Конечный результат должен выглядеть примерно так:

```cpp
COleInsertDialog dlg;
if (dlg.DoModal() != IDOK)
    return;

BeginWaitCursor();

CRectItem* pItem = NULL;
TRY
{
    // First create the C++ object
    pItem = GetDocument()->CreateItem();
    ASSERT_VALID(pItem);

    // Initialize the item from the dialog data.
    if (!dlg.CreateItem(pItem))
        AfxThrowMemoryException();
            // any exception will do
    ASSERT_VALID(pItem);

    // run the object if appropriate
    if (dlg.GetSelectionType() == COleInsertDialog::createNewItem)
        pItem->DoVerb(OLEIVERB_SHOW, this);

    // update right away
    pItem->UpdateLink();
    pItem->UpdateItemRectFromServer();

    // set selection to newly inserted item
    SetSelection(pItem);
    pItem->Invalidate();
}
CATCH (CException, e)
{
    // clean up item
    if (pItem != NULL)
        GetDocument()->DeleteItem(pItem);

    AfxMessageBox(IDP_FAILED_TO_CREATE);
}
END_CATCH

EndWaitCursor();
```

> [!NOTE]
> Вставка нового объекта может отличаться для вашего приложения):

Также необходимо включить элемент \<afxodlgs.h> , который содержит объявление для `COleInsertObject` класса диалогового окна, а также другие стандартные диалоги, предоставляемые MFC.

```Output
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters
```

Эти ошибки вызваны тем, что некоторые константы OLE1 были изменены в OLE 2, даже если в концепции они одинаковы. В этом случае `OLEVERB_PRIMARY` изменился на `OLEIVERB_PRIMARY` . Как в OLE1, так и в OLE 2 Первичная команда обычно выполняется контейнером, когда пользователь дважды щелкает элемент.

Кроме того, `DoVerb` теперь принимает дополнительный параметр — указатель на представление ( `CView` *). Этот параметр используется только для реализации визуального редактирования (или активации на месте). Теперь вы присвойте этому параметру значение NULL, так как в настоящее время вы не реализуете эту функцию.

Чтобы гарантировать, что платформа никогда не пытается выполнить активацию по месту, следует переопределить `COleClientItem::CanActivate` следующим образом:

```cpp
BOOL CRectItem::CanActivate()
{
    return FALSE;
}
```

```Output
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function
```

В MFC/OLE1 `COleClientItem::GetBounds` и `SetBounds` использовались для запроса и обработки экстента элемента ( `left` `top` элементы и всегда равны нулю). В MFC/OLE 2 это более непосредственно поддерживается `COleClientItem::GetExtent` и `SetExtent` , что имеет дело с **размером** или `CSize` вместо этого.

Код для новых вызовов Сетитемректтосервер и Упдатеитемректфромсервер выглядит следующим образом:

```cpp
BOOL CRectItem::UpdateItemRectFromServer()
{
    ASSERT(m_bTrackServerSize);
    CSize size;
    if (!GetExtent(&size))
        return FALSE;    // blank

    // map from HIMETRIC to screen coordinates
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.LPtoDP(&size);
    }
    // just set the item size
    if (m_rect.Size() != size)
    {
        // invalidate the old size/position
        Invalidate();
        m_rect.right = m_rect.left + size.cx;
        m_rect.bottom = m_rect.top + size.cy;
        // as well as the new size/position
        Invalidate();
    }
    return TRUE;
}

BOOL CRectItem::SetItemRectToServer()
{
    // set the official bounds for the embedded item
    CSize size = m_rect.Size();
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.DPtoLP(&size);
    }
    TRY
    {
        SetExtent(size);    // may do a wait
    }
    CATCH(CException, e)
    {
        return FALSE;  // links will not allow SetBounds
    }
    END_CATCH
    return TRUE;
}
```

```Output
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function
```

В большинстве случаев в сценариях синхронные вызовы API MFC/OLE1 из контейнера на сервер *смоделированы*. Прежде чем обрабатывать команды от пользователя, необходимо проверить выполнение ожидающего асинхронного вызова. MFC/OLE1 предоставил `COleClientItem::InWaitForRelease` функцию для этого. В MFC/OLE 2 это не является обязательным, поэтому можно полностью удалить переопределение OnCommand в CMainFrame.

На этом этапе OCLIENT будет компилироваться и компоноваться.

### <a name="other-necessary-changes"></a>Другие необходимые изменения

Тем не менее, это не сделало никаких действий, которые не позволят запустить OCLIENT. Сейчас лучше устранить эти проблемы, а не позже.

Во-первых, необходимо инициализировать библиотеки OLE. Это делается путем вызова `AfxOleInit` из `InitInstance` :

```cpp
if (!AfxOleInit())
{
    AfxMessageBox("Failed to initialize OLE libraries");
    return FALSE;
}
```

Также рекомендуется проверять наличие у виртуальных функций изменений в списке параметров. Одна из таких функций `COleClientItem::OnChange` , переопределенная в каждом приложении-контейнере MFC/OLE. Изучив интерактивную справку, вы увидите, что добавлен дополнительный "DWORD Двпарам". Новый Кректитем:: OnChange выглядит следующим образом:

```cpp
void
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)
{
    if (m_bTrackServerSize && !UpdateItemRectFromServer())
    {
        // Blank object
        if (wNotification == OLE_CLOSED)
        {
            // no data received for the object - destroy it
            ASSERT(!IsVisible());
            GetDocument()->DeleteItem(this);
            return; // no update (item is gone now)
        }
    }
    if (wNotification != OLE_CLOSED)
        Dirty();
    Invalidate();
    // any change will cause a redraw
}
```

В MFC/OLE1 контейнерные приложения производные от класса Document `COleClientDoc` . В MFC/OLE 2 Этот класс был удален и заменен `COleDocument` (Эта новая организация упрощает создание серверных и контейнерных приложений). Существует **#define** , которая сопоставляется с, `COleClientDoc` `COleDocument` чтобы упростить перенос приложений MFC/OLE1 в MFC/OLE 2, например OCLIENT. Одна из функций, не предоставляемых `COleDocument` , была предоставлена `COleClientDoc` стандартными записями схемы командных сообщений. Это делается для того, чтобы серверные приложения, которые также используют `COleDocument` (косвенно), не проводили издержки этих обработчиков команд, если они не являются приложением-контейнером или сервером. Необходимо добавить следующие записи в схему сообщений Кмаиндок:

```cpp
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)
```

Реализация всех этих команд находится в `COleDocument` , который является базовым классом для вашего документа.

На этом этапе OCLIENT является функциональным приложением-контейнером OLE. Можно вставить элементы любого типа (OLE1 или OLE 2). Поскольку код, необходимый для включения встроенной активации, не реализован, элементы редактируются в отдельном окне, подобно OLE1. В следующем разделе обсуждаются необходимые изменения для включения редактирования на месте (иногда называется визуальным редактированием).

### <a name="adding-visual-editing"></a>Добавление "визуального редактирования"

Одной из наиболее интересных функций OLE является активация на месте (или визуальное редактирование). Эта функция позволяет серверному приложению принимать поверхнее часть пользовательского интерфейса контейнера, чтобы предоставить пользователю более простой интерфейс редактирования. Для реализации встроенной активации в OCLIENT необходимо добавить некоторые специальные ресурсы, а также дополнительный код. Эти ресурсы и код обычно предоставляются помощью мастера — на самом деле большая часть кода была взята непосредственно из свежего приложения помощью мастера с поддержкой "контейнера".

Во-первых, необходимо добавить ресурс меню, который будет использоваться при наличии элемента, который находится в активном месте. Этот дополнительный ресурс меню можно создать в Visual C++ путем копирования IDR_OCLITYPE ресурса и удаления всех всплывающих окон файлов и окон. Между всплывающими окнами файла и окна вставляются две разделители, чтобы указать разделение групп (оно должно выглядеть так: файл &#124;&#124; окно). Дополнительные сведения о том, что означают эти разделители и как объединяются меню сервера и контейнера, см. в [меню и ресурсах](../mfc/menus-and-resources-menu-merging.md).

После создания этих меню необходимо сообщить платформе о них. Это делается путем вызова `CDocTemplate::SetContainerInfo` для шаблона документа перед добавлением его в список шаблонов документов в InitInstance. Новый код для регистрации шаблона документа выглядит следующим образом:

```cpp
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE,
    RUNTIME_CLASS(CMainDoc),
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```

Ресурс IDR_OLECLITYPE_INPLACE — это специальный ресурс на месте, созданный в Visual C++.

Чтобы включить активацию на месте, необходимо изменить как `CView` производный класс (кмаинвиев), так и `COleClientItem` производный класс (кректитем). Все эти переопределения предоставляются помощью мастера, и большая часть реализации будет происходить непосредственно из приложения помощью мастера по умолчанию.

На первом шаге этого порта активация на месте была полностью отключена путем переопределения `COleClientItem::CanActivate` . Это переопределение следует удалить, чтобы разрешить активацию на месте. Кроме того, значение NULL было передано всем вызовам метода `DoVerb` (существует два из них), поскольку предоставление представления было необходимо только для активации на месте. Чтобы полностью реализовать активацию на месте, необходимо передать правильное представление в `DoVerb` вызове. Один из этих вызовов `CMainView::OnInsertObject` :

```cpp
pItem->DoVerb(OLEIVERB_SHOW, this);
```

Другой — в `CMainView::OnLButtonDblClk` :

```cpp
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```

Необходимо переопределить `COleClientItem::OnGetItemPosition` . Это указывает серверу, куда поместить свое окно относительно окна контейнера, когда элемент активирован на месте. Для OCLIENT реализация является тривиальной:

```cpp
void CRectItem::OnGetItemPosition(CRect& rPosition)
{
    rPosition = m_rect;
}
```

Большинство серверов также реализуют то, что называется «изменение размера на месте». Это позволяет изменять размеры и перемещать окно сервера, когда пользователь редактирует элемент. Контейнер должен участвовать в этом действии, так как перемещение или изменение размера окна обычно влияет на расположение и размер в самом документе контейнера. Реализация для OCLIENT синхронизирует внутренний прямоугольник, поддерживаемый m_rect, с новым положением и размером.

```cpp
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)
{
    ASSERT_VALID(this);

    if (!COleClientItem::OnChangeItemPosition(rectPos))
        return FALSE;

    Invalidate();
    m_rect = rectPos;
    Invalidate();
    GetDocument()->SetModifiedFlag();

    return TRUE;
}
```

На этом этапе имеется достаточный код, позволяющий активировать элемент на месте и работать с изменением размера и перемещением элемента, когда он активен, но никакой код не позволит пользователю выйти из сеанса редактирования. Хотя некоторые серверы предоставляют эти функции самостоятельно, обрабатывая escape-клавишу, мы предлагаем, что контейнеры предоставляют два способа деактивации элемента: (1), щелкнув за пределами элемента, и (2) нажав клавишу ESCAPE.

Для клавиши ESCAPE добавьте ускоритель с Visual C++, который сопоставляет ключ VK_ESCAPE с командой, ID_CANCEL_EDIT добавляется к ресурсам. Обработчик для этой команды выглядит следующим образом:

```cpp
// The following command handler provides the standard
// keyboard user interface to cancel an in-place
// editing session.void CMainView::OnCancelEdit()
{
    // Close any in-place active item on this view.
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->Close();
    ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);
}
```

Чтобы обрабатывался случай, когда пользователь щелкает за пределами элемента, добавьте следующий код в начало `CMainView::SetSelection` :

```cpp
if (pNewSel != m_pSelection || pNewSel == NULL)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL&& pActiveItem != pNewSel)
        pActiveItem->Close();
}
```

Когда элемент находится в активном месте, он должен иметь фокус. Чтобы убедиться в том, что вы обрабатываете OnSetFocus, чтобы фокус всегда передавался активному элементу, когда представление получает фокус:

```cpp
// Special handling of OnSetFocus and OnSize are required
// when an object is being edited in-place.
void CMainView::OnSetFocus(CWnd* pOldWnd)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);

    if (pActiveItem != NULL &&
        pActiveItem->GetItemState() == COleClientItem::activeUIState)
    {
        // need to set focus to this item if it is same view
        CWnd* pWnd = pActiveItem->GetInPlaceWindow();
        if (pWnd != NULL)
        {
            pWnd->SetFocus();   // don't call the base class
            return;
        }
    }

    CView::OnSetFocus(pOldWnd);
}
```

При изменении размера представления необходимо уведомить активный элемент о том, что прямоугольник обрезки изменился. Для этого необходимо предоставить обработчик для `OnSize` :

```cpp
void CMainView::OnSize(UINT nType, int cx, int cy)
{
    CView::OnSize(nType, cx, cy);
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->SetItemRects();
}
```

## <a name="case-study-hiersvr-from-mfc-20"></a>Пример внедрения: HIERSVR из MFC 2,0

[HIERSVR](../overview/visual-cpp-samples.md) также входит в MFC 2,0 и реализует OLE с MFC/OLE1. В этом заметке кратко описаны шаги, по которым приложение было первоначально преобразовано для использования классов MFC/OLE 2. После завершения первоначального порта было добавлено несколько компонентов, чтобы лучше продемонстрировать классы MFC/OLE 2. Эти функции не будут рассматриваться здесь. Дополнительные сведения об этих дополнительных возможностях см. в этом образце.

> [!NOTE]
> Ошибки и пошаговые процессы компилятора были созданы с Visual C++ 2,0. Конкретные сообщения об ошибках и расположения могли быть изменены с Visual C++ 4,0, но концептуальные сведения остаются действительными.

### <a name="getting-it-up-and-running"></a>Подготовка и запуск

Подход, выполняемый для переноса примера HIERSVR в MFC/OLE, заключается в том, чтобы начать с его сборки и исправить очевидные ошибки компилятора, которые могут возникнуть. Если взять пример с MFC 2,0 и скомпилировать его в этой версии MFC, вы обнаружите, что не много ошибок, которые можно устранить (хотя это не так, как в образце OCLIENT). Ошибки в порядке, в котором они обычно возникают, описаны ниже.

### <a name="compile-and-fix-errors"></a>Компиляция и исправление ошибок

```Output
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'
```

Эта первая ошибка указывает на гораздо большую проблему с `InitInstance` функцией для серверов. Инициализация, необходимая для OLE-сервера, возможно, является одним из крупнейших изменений, которые необходимо внести в приложение MFC или OLE1 для его запуска. Лучше всего узнать, что помощью мастера создает для OLE-сервера и изменить код соответствующим образом. Ниже приведены некоторые моменты, которые следует учитывать.

Для инициализации библиотек OLE необходимо вызвать метод `AfxOleInit`

Вызовите Сетсерверинфо для объекта шаблона документа, чтобы задать дескрипторы ресурсов сервера и сведения о классе среды выполнения, которые нельзя задать с помощью `CDocTemplate` конструктора.

Не показывать главное окно приложения, если параметром/Embedding есть в командной строке.

Для документа потребуется **идентификатор GUID** . Это уникальный идентификатор для типа документа (128 бит). Помощью мастера создаст его. Если вы используете методику, описанную в статье о копировании нового кода из нового серверного приложения помощью мастера, можно просто «украсть» идентификатор GUID из этого приложения. В противном случае можно использовать служебную программу GUIDGEN.EXE в каталоге BIN.

Необходимо подключить `COleTemplateServer` объект к шаблону документа, вызвав метод `COleTemplateServer::ConnectTemplate` .

Обновите системный реестр, если приложение выполняется автономно. Таким образом, если пользователь переместит. EXE для вашего приложения, запуская его из нового расположения, обновит базу данных регистрации системы Windows, чтобы она указывала на новое расположение.

После применения всех этих изменений в зависимости от того, что создает помощью мастера `InitInstance` , `InitInstance` (и связанный GUID) для HIERSVR должен читаться следующим образом:

```cpp
// this is the GUID for HIERSVR documents
static const GUID BASED_CODE clsid =
{ 0xA0A16360L, 0xC19B, 0x101A, { 0x8C, 0xE5, 0x00, 0xDD, 0x01, 0x11, 0x3F, 0x12 } };

/////////////////////////////////////////////////////////////////////////////
// COLEServerApp initialization

BOOL COLEServerApp::InitInstance()
{
    // OLE 2 initialization
    if (!AfxOleInit())
    {
        AfxMessageBox("Initialization of the OLE failed!");
        return FALSE;
    }

    // Standard initialization
    LoadStdProfileSettings();   // Load standard INI file options

    // Register document templates
    CDocTemplate* pDocTemplate;
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,
        RUNTIME_CLASS(CServerDoc),
        RUNTIME_CLASS(CMDIChildWnd),
        RUNTIME_CLASS(CServerView));
    pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);
    AddDocTemplate(pDocTemplate);

    // create main MDI Frame window
    CMainFrame* pMainFrame = new CMainFrame;
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))
        return FALSE;
    m_pMainWnd = pMainFrame;

    SetDialogBkColor(); // gray look

    // enable file manager drag/drop and DDE Execute open
    m_pMainWnd->DragAcceptFiles();
    EnableShellOpen();

    m_server.ConnectTemplate(clsid, pDocTemplate, FALSE);
    COleTemplateServer::RegisterAll();

    // try to launch as an OLE server
    if (RunEmbedded())
    {
        // "short-circuit" initialization -- run as server!
        return TRUE;
    }
    m_server.UpdateRegistry();
    RegisterShellFileTypes();

    // not run as OLE server, so show the main window
    if (m_lpCmdLine[0] == '\0')
    {
        // create a new (empty) document
        OnFileNew();
    }
    else
    {
        // open an existing document
        OpenDocumentFile(m_lpCmdLine);
    }

    pMainFrame->ShowWindow(m_nCmdShow);
    pMainFrame->UpdateWindow();

    return TRUE;
}
```

Вы увидите, что приведенный выше код ссылается на новый идентификатор ресурса, IDR_HIERSVRTYPE_SRVR_EMB. Это ресурс меню, который будет использоваться при редактировании документа, внедренного в другой контейнер. В MFC/OLE1 пункты меню, относящиеся к редактированию внедренного элемента, были изменены в режиме реального времени. Использование совершенно другой структуры меню при редактировании внедренного элемента вместо редактирования файлового документа значительно упрощает предоставление различных пользовательских интерфейсов для этих двух отдельных режимов. Как вы увидите позже, при редактировании внедренного объекта используется полностью отдельный ресурс меню.

Чтобы создать этот ресурс, загрузите сценарий ресурса в Visual C++ и скопируйте существующий ресурс меню IDR_HIERSVRTYPE. Переименуйте новый ресурс в IDR_HIERSVRTYPE_SRVR_EMB (это то же соглашение об именовании, которое использует помощью мастера). Затем измените "сохранить файл" на "обновление файла"; Укажите идентификатор команды ID_FILE_UPDATE. Также измените «файл сохранить как» на «файл сохранить копию как»; Укажите идентификатор команды ID_FILE_SAVE_COPY_AS. Платформа предоставляет реализацию обеих этих команд.

```Output
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers
```

Существует ряд ошибок, вызванных переопределением `OnSetData` , так как он ссылается на тип **олестатус** . **Олестатус** был таким способом, OLE1 возвращали ошибки. Это изменилось на **HRESULT** в OLE 2, хотя MFC обычно преобразует **HRESULT** в объект, `COleException` содержащий ошибку. В этом конкретном случае переопределение `OnSetData` больше не требуется, поэтому проще всего удалить его.

```Output
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters
```

`COleServerItem`Конструктор принимает дополнительный параметр "bool". Этот флаг определяет, как выполняется управление памятью для `COleServerItem` объектов. Если задать для него значение TRUE, то платформа обрабатывает управление памятью этих объектов, удаляя их, когда они больше не нужны. HIERSVR использует `CServerItem` объекты (производные от `COleServerItem` ) как часть собственных данных, поэтому этот флаг устанавливается в значение false. Это позволяет HIERSVR определить время удаления каждого элемента сервера.

```Output
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
```

Так как эти ошибки предполагаются, существуют некоторые функции "чистого виртуального", которые не были переопределены в Ксерверитем. Скорее всего, это вызвано тем, что изменился список параметров OnDraw. Чтобы устранить эту ошибку, измените `CServerItem::OnDraw` следующим образом (а также объявление в свритем. h):

```cpp
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)
{
    // request from OLE to draw node
    pDC->SetMapMode(MM_TEXT); // always in pixels
    return DoDraw(pDC, CPoint(0, 0), FALSE);
}
```

Новый параметр — "rSize". Это позволяет заполнять размер рисунка, если это удобно. Этот размер должен быть в **HIMETRIC**. В этом случае неудобно заполнить это значение в, поэтому платформа вызывает метод `OnGetExtent` для получения экстента. Чтобы это работало, необходимо реализовать `OnGetExtent` :

```cpp
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect, CSize& rSize)
{
    if (dwDrawAspect != DVASPECT_CONTENT)
        return COleServerItem::OnGetExtent(dwDrawAspect, rSize);

    rSize = CalcNodeSize();
    return TRUE;
}
```

```Output
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'
```

В функции Ксерверитем:: Калкнодесизе размер элемента преобразуется в **HIMETRIC** и сохраняется в *m_rectBounds*. Недокументированный элемент "*m_rectBounds*" `COleServerItem` не существует (он был частично заменен *m_sizeExtentом*, но в OLE 2 этот член немного отличается от использования *m_rectBounds* в OLE1). Вместо установки размера **HIMETRIC** в эту переменную члена вы вернете его. Это возвращаемое значение используется в `OnGetExtent` , реализованном ранее.

```cpp
CSize CServerItem::CalcNodeSize()
{
    CClientDC dcScreen(NULL);

    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,
        m_strDescription.GetLength());
    m_sizeNode += CSize(CX_INSET * 2, CY_INSET * 2);

    // set suggested HIMETRIC size
    CSize size(m_sizeNode.cx, m_sizeNode.cy);
    dcScreen.SetMapMode(MM_HIMETRIC);
    dcScreen.DPtoLP(&size);
    return size;
}
```

Ксерверитем также переопределяет `COleServerItem::OnGetTextData` . Эта функция устарела в MFC/OLE и заменяется другим механизмом. Версия MFC 3,0 в примере для MFC OLE в версии [HIERSVR](../overview/visual-cpp-samples.md) реализует эту функцию путем переопределения `COleServerItem::OnRenderFileData` . Эта функция не имеет значения для этого базового порта, поэтому можно удалить переопределение Онжеттекстдата.

В свритем. cpp имеется гораздо больше ошибок, которые не были устранены. Они не являются "реальными" ошибками — только ошибки, вызванные предыдущими ошибками.

```Output
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters
```

`COleServerItem::CopyToClipboard` больше не поддерживает `bIncludeNative` флаг. Собственные данные (данные, записываемые функцией сериализации серверного элемента) всегда копируются, поэтому первый параметр удаляется. Кроме того, `CopyToClipboard` вызовет исключение при возникновении ошибки вместо возвращения значения false. Измените код для Ксервервиев:: Онедиткопи следующим образом:

```cpp
void CServerView::OnEditCopy()
{
    if (m_pSelectedNode == NULL)
        AfxThrowNotSupportedException();

    TRY
    {
        m_pSelectedNode->CopyToClipboard(TRUE);
    }
    CATCH_ALL(e)
    {
        AfxMessageBox("Copy to clipboard failed");
    }
    END_CATCH_ALL
}
```

Несмотря на то, что в результате компиляции версии объекта HIERSVR MFC 2,0 возникли ошибки, чем для той же версии OCLIENT, на самом деле было меньше изменений.

На этом этапе HIERSVR будет компилироваться и связываться и работать как OLE-сервер, но без функции редактирования на месте, которая будет реализована далее.

### <a name="adding-visual-editing"></a>Добавление "визуального редактирования"

Чтобы добавить в это серверное приложение "визуальное редактирование" (или активацию на месте), необходимо выполнить только некоторые действия.

- Вам понадобится специальный ресурс меню, который будет использоваться, когда элемент находится в активном месте.

- В этом приложении есть панель инструментов, поэтому для соответствия команд меню, доступных на сервере (совпадает с упомянутым выше ресурсом меню), требуется панель инструментов с подмножеством обычной панели инструментов.

- Необходим новый класс, производный от `COleIPFrameWnd` , который предоставляет пользовательский интерфейс на месте (подобно мере, производный от класса CMainFrame `CMDIFrameWnd` ), предоставляющий пользовательский интерфейс MDI.

- Необходимо сообщить платформе об этих специальных ресурсах и классах.

Ресурс меню легко создать. Запустите Visual C++, скопируйте ресурс меню IDR_HIERSVRTYPE в ресурс меню с именем IDR_HIERSVRTYPE_SRVR_IP. Измените меню так, чтобы в меню "Правка" и "Справка" остались только всплывающие окна. Добавьте два разделителя в меню "Правка" и "Справка" (оно должно выглядеть следующим образом: изменить справку &#124;&#124; ). Дополнительные сведения о том, что означают эти разделители и как объединяются меню сервера и контейнера, см. в разделе меню [и ресурсы: слияние меню](../mfc/menus-and-resources-menu-merging.md).

Точечный рисунок для панели инструментов подмножества можно легко создать, скопировав его из нового приложения, созданного помощью мастера, с установленным параметром "сервер". Затем это битовое изображение можно импортировать в Visual C++. Не забудьте присвоить точечному рисунку идентификатор IDR_HIERSVRTYPE_SRVR_IP.

Класс, производный от, `COleIPFrameWnd` можно скопировать из созданного помощью мастера приложения с поддержкой сервера. Скопируйте оба файла, ИПФРАМЕ. CPP и ИПФРАМЕ. H и добавьте их в проект. Убедитесь, что `LoadBitmap` вызов ссылается на IDR_HIERSVRTYPE_SRVR_IP, точечный рисунок, созданный на предыдущем шаге.

Теперь, когда все новые ресурсы и классы созданы, добавьте необходимый код, чтобы платформа знала о них (и знает, что это приложение теперь поддерживает редактирование на месте). Это можно сделать, добавив еще несколько параметров в `SetServerInfo` вызов `InitInstance` функции:

```cpp
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```

Теперь она готова к выполнению на месте в любом контейнере, который также поддерживает встроенную активацию. Но в коде еще одна незначительная ошибка по-прежнему скрывающиеся. HIERSVR поддерживает контекстное меню, отображаемое при нажатии пользователем правой кнопки мыши. Это меню работает, когда HIERSVR открыто полностью, но не работает при редактировании внедренного объекта. Причина может быть закреплена за этой одной строкой кода в Ксервервиев:: Онрбуттондовн:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```

Обратите внимание на ссылку `AfxGetApp()->m_pMainWnd` . Когда сервер активирован на месте, он имеет главное окно, а m_pMainWnd установлен, но обычно невидима. Кроме того, это окно относится к *главному* окну приложения — окну фрейма MDI, которое появляется, когда сервер полностью открыт или работает автономно. Он не ссылается на активное окно фрейма, которое, когда активировано по месту, является окном фрейма, производным от `COleIPFrameWnd` . Чтобы получить правильное активное окно даже при редактировании на месте, эта версия MFC добавляет новую функцию `AfxGetMainWnd` . Как правило, эту функцию следует использовать вместо `AfxGetApp()->m_pMainWnd` . Этот код необходимо изменить следующим образом:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetMainWnd());
```

Теперь у вас минимально включенный OLE-сервер для функциональной активации на месте. Но существует множество функций, доступных в MFC/OLE 2, которые не были доступны в MFC/OLE1. Дополнительные сведения о функциях, которые можно реализовать, см. в образце HIERSVR. Ниже перечислены некоторые функции, реализованные в HIERSVR.

- Масштаб для истинного поведения WYSIWYG относительно контейнера.

- Перетаскивание и пользовательского формата буфера обмена.

- Прокрутка окна контейнера при изменении выбора.

В образце HIERSVR в MFC 3,0 также используется немного другая структура серверных элементов. Это помогает экономить память и повышает гибкость ссылок. В 2,0 версии HIERSVR каждый узел в дереве *имеет значение-a* `COleServerItem` . `COleServerItem` содержит немного больше издержек, чем строго требуется для каждого из этих узлов, но `COleServerItem` требуется для каждой активной ссылки. Но в большинстве случаев в любой момент времени есть несколько активных ссылок. Чтобы сделать это более эффективным, HIERSVR в этой версии MFC отделяет узел от `COleServerItem` . У него есть как Ксерверноде, так и `CServerItem` класс. `CServerItem`(Производный от `COleServerItem` ) создается только при необходимости. Когда контейнер (или контейнеры) перестают использовать эту конкретную ссылку на этот конкретный узел, объект Ксерверитем, связанный с Ксерверноде, удаляется. Такая схема является более эффективной и гибкой. Гибкость достигается при работе с несколькими ссылками выбора. Ни одна из этих двух версий HIERSVR не поддерживает множественный выбор, но было бы гораздо проще добавить (и поддерживать ссылки на такие варианты) с помощью версии MFC 3,0 HIERSVR, поскольку `COleServerItem` отделена от собственных данных.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категориям](../mfc/technical-notes-by-category.md)
