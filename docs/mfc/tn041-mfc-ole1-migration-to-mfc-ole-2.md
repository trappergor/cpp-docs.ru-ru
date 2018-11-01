---
title: 'Tn041: миграция MFC-Ole1 на MFC-OLE 2'
ms.date: 10/18/2018
f1_keywords:
- vc.mfc.ole
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
ms.openlocfilehash: 2bdf0c353151c8e932b3e8641a72b2116c45f3f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568529"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041. Миграция MFC/OLE1 на MFC/OLE 2

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

## <a name="general-issues-relating-to-migration"></a>Общие проблемы, относящиеся к миграции

Одной из целей проектирования для классов OLE 2 в MFC 2.5 (и более поздних версий) было сохранить большую часть ту же архитектуру, внедряемых в MFC 2.0 для поддержки OLE 1.0. Таким образом, многие из те же классы OLE в MFC 2.0 по-прежнему существуют в эту версию MFC (`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`). Кроме того многие из API-интерфейсов в этих классах, одинаковы. Тем не менее OLE 2 кардинально отличающуюся от OLE 1.0, и вы можете ожидать, что некоторые сведения были изменены. Если вы знакомы с поддержкой OLE1 на MFC 2.0, вы будете чувствовать себя непринужденно с доступной в MFC поддержки 2.0.

Если вы являетесь перевод существующего приложения MFC/OLE1 и добавление функциональных возможностей OLE 2 к нему, вы сначала Прочитайте эту заметку. Эта заметка рассматриваются некоторые общие проблемы, возникающие в процессе переноса вашей функции OLE1 на MFC/OLE 2 и затем рассматривается проблем, обнаруженных при переносе два приложения, включенные в MFC 2.0: в примерах MFC OLE [OCLIENT](../visual-cpp-samples.md) и [HIERSVR](../visual-cpp-samples.md).

## <a name="mfc-documentview-architecture-is-important"></a>Важно архитектуры документ/представление MFC

Если приложение использует архитектуру документ/представление MFC и вы хотите добавить поддержку OLE 2 в приложении, пришло время для перемещения для документов и представлений. Преимущества классов MFC OLE 2 достигается только тогда, когда приложение использует встроенные архитектуру и компоненты MFC.

Реализация сервера или контейнера без использования MFC архитектуры можно, но не рекомендуется.

## <a name="use-mfc-implementation-instead-of-your-own"></a>Используйте вместо собственных реализация MFC

Классы MFC «canned реализации», такие как `CToolBar`, `CStatusBar`, и `CScrollView` имеют встроенные вариантов специального кода для поддержки OLE 2. Таким образом Если эти классы можно использовать в приложении вас приятно удивит усилия, уходящие на их, чтобы ознакомить их OLE. Опять же существует возможность «сводный собственной» здесь классы для этих целей, но не рекомендуется. Если необходимо реализовать аналогичные функциональные возможности, исходный код MFC предоставляет для работы с некоторыми более точно точки OLE (особенно когда дело доходит до активации на месте).

## <a name="examine-the-mfc-sample-code"></a>Проверьте код MFC, пример

Существует ряд примеров MFC, которые включают функции OLE. Каждый из этих приложений реализует OLE с другого ракурса.

- [HIERSVR](../visual-cpp-samples.md) предназначен главным образом для использования в качестве серверного приложения. Оно было включено в MFC 2.0 как приложение MFC/OLE1 и перенесена в MFC/OLE 2 и затем расширенных таким образом, что он реализует OLE доступных возможностей OLE 2.

- [OCLIENT](../visual-cpp-samples.md) это приложение изолированного контейнера, предназначена для демонстрации многие функции OLE с точки зрения контейнера. Он слишком был перенесен из MFC 2.0 и затем расширить для поддержки многих более сложных функций OLE, таких как форматы буфера обмена настраиваемых и ссылки на внедренные элементы.

- [ФУНКЦИЙ](../visual-cpp-samples.md) это приложение реализует поддержка контейнера OLE гораздо как OCLIENT, за исключением того, что она делает это в рамках объектно ориентированного рисования программу. Оно показано, как может реализовывать поддержку контейнера OLE и интегрировать его в существующее приложение.

- [SUPERPAD](../visual-cpp-samples.md) этого приложения, а также выполняется нормально автономного приложения, также является OLE-сервер. Поддержка сервера, который он реализует является довольно минималистском. Особый интерес представляет использование служб OLE буфера обмена для копирования данных в буфер обмена, но использует функции, встроенные в элемент управления Windows «изменить» для реализации функциональных возможностей вставки в буфер обмена. Это показывает интересных сочетание традиционных использования Windows API, а также интеграции с помощью новых API-интерфейсы OLE.

Дополнительные сведения об образцах приложений см. в разделе «MFC образец справку».

## <a name="case-study-oclient-from-mfc-20"></a>Практический пример: OCLIENT из MFC 2.0

Как уже говорилось ранее, [OCLIENT](../visual-cpp-samples.md) был включен в MFC 2.0 и реализации OLE с MFC/OLE1. Ниже приведено описание этапов, по которым это приложение изначально был преобразован для использования классов MFC/OLE 2. Ряд функций были добавлены после завершения начального порта для лучшей иллюстрации классы MFC/OLE. Эти функции не будут рассматриваться ниже; ссылаться на сам образец Дополнительные сведения по этим дополнительным возможностям.

> [!NOTE]
> Ошибки компилятора и пошаговый процесс создания с помощью Visual C++ 2.0. Сообщения об ошибках и расположения могло измениться с Visual C++ 4.0, но основные данные остается допустимым.

## <a name="getting-it-up-and-running"></a>Обеспечение эффективности и запуск

Подход к порту Образец OCLIENT на MFC/OLE — запуск с его создания и устранение ошибок очевидным компилятора, которые будут вызывать. Если взять пример OCLIENT 2.0 MFC и скомпилировать его в эту версию MFC, обнаружится, что не отсутствуют ошибки, что многие. Ниже приведено описание ошибки в порядке их возникновения.

## <a name="compile-and-fix-errors"></a>Исправление ошибки компиляции и

```Output
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters
```

Ошибка задач `COleClientItem::Draw`. В MFC/OLE1 потребовалось несколько параметров, чем версия MFC/OLE принимает. Лишние параметры были часто не требуется и обычно NULL (как в этом примере). Эта версия MFC может автоматически определить значения для lpWBounds при CDC, который рисуется на метафайл контроллера домена. Кроме того параметр pFormatDC больше не является обязательным, так как платформа создаст одно из «атрибута контроллера домена» основной контроллер домена, переданный. Поэтому чтобы устранить эту проблему, просто удалите два дополнительных NULL параметров вызова Draw.

```Output
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier
\oclient\mainview.cpp(273) : error C2057: expected constant expression
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
```

Ошибки выше результат из-за того, все `COleClientItem::CreateXXXX` функциям в MFC/OLE1, необходимым передачу уникальное имя для представления элемента. Это было требование для базового OLE интерфейса API. Это не является обязательным в MFC/OLE 2, так как OLE 2 не использует DDE в качестве базового механизма связи (имя использовалось в диалогов DDE). Чтобы устранить эту проблему, можно удалить `CreateNewName` функции, а также все ссылки на него. Это легко узнать, что каждая функция MFC/OLE ожидает в этой версии достаточно поместить курсор на вызов и нажать клавишу F1.

Еще одна область, которая существенно отличается — обработка буфера обмена OLE 2. С OLE1 вы использовали буфере Windows API-интерфейсы взаимодействия с буфером обмена. С помощью OLE 2 это делается с помощью другого механизма. API-интерфейсов MFC/OLE1 предполагается, что буфер обмена был открыт перед копированием `COleClientItem` объектов в буфер обмена. Это больше не требуется и вызовет переход на другой все операции с буфером обмена MFC/OLE. Когда вы редактируете код для удаления зависимостей на `CreateNewName`, следует удалить код, который открывает и закрывает в буфер обмена Windows.

```Output
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function
\oclient\mainview.cpp(344) : error C2057: expected constant expression
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'
```

Эти ошибки в результате `CMainView::OnInsertObject` обработчика. Обработка команды «Вставка объекта» — это еще одна область, где изменений довольно. В этом случае проще просто дополнить исходной реализации, предоставляемые мастером приложений для нового приложения OLE-контейнера. На самом деле это методика, которую можно применить к переносу других приложений. В MFC/OLE1, отображается диалоговое окно «Вставка объекта» путем вызова `AfxOleInsertDialog` функции. В этой версии конструкцию `COleInsertObject` диалоговое окно и вызовите `DoModal`. Кроме того, новые элементы OLE создаются с помощью **CLSID** вместо строки имени класса. Конечный результат должен выглядеть следующим образом

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

Это также необходимо включить \<afxodlgs.h >, который содержит объявление для `COleInsertObject` класса диалогового окна, а также другие стандартные диалоговые окна MFC.

```Output
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters
```

Эти ошибки вызваны тот факт, что были изменены некоторые константы OLE1 в OLE 2, несмотря на то, что в концепции они совпадают. В этом случае `OLEVERB_PRIMARY` изменилось на `OLEIVERB_PRIMARY`. В OLE1 и OLE 2 первичный глагол обычно выполняется в контейнере при двойном щелчке элемента.

Кроме того `DoVerb` теперь принимает дополнительный параметр — указатель на представление (`CView`*). Этот параметр используется только для реализации «Визуальное редактирование» (или активации на месте). Сейчас можно задать для этого параметра значение NULL, так как эта функция в настоящее время не реализуется.

Чтобы убедиться в том, что платформа никогда не пытается на месте активировать, нужно переопределить `COleClientItem::CanActivate` следующим образом:

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

В MFC/OLE1 `COleClientItem::GetBounds` и `SetBounds` запросов и управление ими объем элемент использовались ( `left` и `top` члены всегда равны нулю). В MFC/OLE 2 это напрямую поддерживает `COleClientItem::GetExtent` и `SetExtent`, что иметь дело с **размер** или `CSize` вместо этого.

Код для вашего нового SetItemRectToServer, и вызовы UpdateItemRectFromServer выглядеть следующим образом:

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

В синхронных API MFC/OLE1 вызовов из контейнера сервера были *имитации*, так как OLE1 была асинхронная во многих случаях. Он был необходим на наличие ожидающих асинхронный вызов выполняется перед обработкой команды от пользователя. MFC/OLE1 предоставленный `COleClientItem::InWaitForRelease` функции для этого. В MFC/OLE 2 это необязательно, чтобы можно было удалить переопределение метода OnCommand в CMainFrame все вместе.

На этом этапе OCLIENT будет скомпилировать и связать.

## <a name="other-necessary-changes"></a>Другие необходимые изменения.

Несколько моментов, которые не выполняются, которые обеспечат OCLIENT применялось, тем не менее. Лучше устранить проблемы теперь вместо более поздней версии.

Во-первых бывает необходимо инициализировать библиотеки OLE. Это делается путем вызова `AfxOleInit` из `InitInstance`:

```cpp
if (!AfxOleInit())
{
    AfxMessageBox("Failed to initialize OLE libraries");
    return FALSE;
}
```

Также рекомендуется проверить виртуальные функции для изменения списка параметров. Одна такая функция является `COleClientItem::OnChange`, переопределенный в каждое приложение контейнера MFC/OLE. Просмотрев справку в Интернете, вы увидите, что был добавлен дополнительный «DWORD dwParam». Новый CRectItem::OnChange выглядит следующим образом:

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

В MFC/OLE1, приложения-контейнеры производный класс документа из `COleClientDoc`. В MFC/OLE 2 этот класс удален и заменен `COleDocument` (это новая организация упрощает создание контейнера и сервера приложений). Существует **#define** , сопоставляющий `COleClientDoc` для `COleDocument` для упрощения переноса приложений MFC/OLE1 на MFC/OLE 2, например OCLIENT. Одна из функций, не предоставляемые `COleDocument` , предоставленным `COleClientDoc` — это стандартная команда сообщение записей карты. Это делается так, серверных приложений, которые также используют `COleDocument` (косвенно), без выполнения с ними затраты на эти обработчики команд пока не будут приложения контейнера и сервера. Необходимо добавить следующие записи в схеме сообщений CMainDoc:

```cpp
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)
```

Все эти команды реализуется в `COleDocument`, который является базовым классом для документа.

На этом этапе OCLIENT — это функциональное приложение контейнера OLE. Существует возможность вставлять элементы любого типа (OLE1 или OLE 2). Так как не реализуется необходимый код для включения активации на месте, в отдельном окне большая, как с помощью OLE1 редактировать элементы. В следующем разделе объясняется необходимые изменения, чтобы включить редактирование на месте (иногда называется «Визуальное редактирование»).

## <a name="adding-visual-editing"></a>Добавление «Визуальное редактирование»

Одним из самых интересных возможностей бюллетеня OLE является встроенной активации (или «Визуального редактирования»). Эта функция позволяет перехватить частей контейнера пользовательского интерфейса к предоставлен более удобный интерфейс редактирования для пользователя, серверное приложение. Для реализации встроенной активации для OCLIENT, некоторые специальные ресурсы должны быть добавлены, а также дополнительный код. Эти ресурсы и код обычно предоставляются мастером приложений AppWizard, на самом деле, большая часть кода здесь заимствованных непосредственно из нового приложения мастером приложений с поддержкой «Container».

Во-первых необходимо добавить ресурс меню, чтобы использовать, если элемент, который активен на месте. Этот ресурс дополнительные меню в Visual C++ можно создать путем копирования ресурсов IDR_OCLITYPE и удалив все, кроме файлов и окно всплывающих окон. Два разделителей вставляется разделитель файла и окно всплывающих окон для указания разделение группы (результат будет выглядеть так: файл &#124; &#124; окна). Дополнительные сведения о значении этих разделителей и способ слияния меню сервера и контейнера см. в разделе [меню и ресурсы: слияние меню](../mfc/menus-and-resources-menu-merging.md).

Получив эти меню создан, необходимо платформа узнала о них. Это делается путем вызова `CDocTemplate::SetContainerInfo` для шаблона документа перед их добавлением в список шаблонов документов в InitInstance. Новый код для регистрации шаблона документа выглядит следующим образом:

```cpp
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE,
    RUNTIME_CLASS(CMainDoc),
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```

На IDR_OLECLITYPE_INPLACE это специальный ресурс на месте, созданные в Visual C++.

Для включения активации на месте, есть несколько моментов, которые потребуется изменить в обоих `CView` (CMainView) производного класса, а также `COleClientItem` производного класса (CRectItem). Все эти переопределения предоставляются мастером приложений AppWizard и большую часть реализации поступают непосредственно из приложения по умолчанию мастером приложений.

На первом шаге этого порта, встроенной активации отключена полностью путем переопределения `COleClientItem::CanActivate`. Это переопределение должны быть удалены, чтобы разрешить активацию на месте. Кроме того, было передано значение NULL для всех вызовов `DoVerb` (существует два из них), так как предоставляющий представление требовалось только для активации на месте. Для полной реализации встроенной активации, необходимые для передачи в правильный режим `DoVerb` вызова. Одна из этих вызовов `CMainView::OnInsertObject`:

```cpp
pItem->DoVerb(OLEIVERB_SHOW, this);
```

Другой пример — `CMainView::OnLButtonDblClk`:

```cpp
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```

Необходимо переопределить `COleClientItem::OnGetItemPosition`. Это указывает, что сервер для размещения окна ее относительно окна контейнера, если элемент является активироваться на месте. Для OCLIENT реализация предельно проста:

```cpp
void CRectItem::OnGetItemPosition(CRect& rPosition)
{
    rPosition = m_rect;
}
```

Кроме того, большинство серверов реализовать так называемый «на месте изменения размера.» Это позволяет окне сервера, изменять размеры и перемещены, когда пользователь редактирует элемент. Контейнера должны быть включены в это действие, так как при перемещении или изменении размера окна обычно влияет на положение и размер в рамках самого документа контейнера. Реализация OCLIENT синхронизирует внутренней обслуживается m_rect новое положение и размер прямоугольника.

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

На этом этапе имеется код, чтобы разрешить элемент быть активироваться на месте, так и для изменения размеров и перемещение элемента, когда он включен, но код не позволит пользователю для выхода из сеанса редактирования. Несмотря на то, что некоторые серверы будет предоставлять эту функцию самостоятельно обрабатывая нажмите клавишу ESC, предполагается, что контейнеры предоставляют два способа отключить элемент: (1), щелкнув за пределами элемента или (2), нажав клавишу ESC.

Нажмите клавишу ESC добавить ускоритель с Visual C++, который сопоставляется клавиша VK_ESCAPE команды, ID_CANCEL_EDIT добавляется к ресурсам. Обработчик для этой команды выглядит следующим образом:

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

Для обработки случая, когда пользователь щелкает вне элемента, добавьте следующий код в начало `CMainView::SetSelection`:

```cpp
if (pNewSel != m_pSelection || pNewSel == NULL)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL&& pActiveItem != pNewSel)
        pActiveItem->Close();
}
```

Если элемент активен на месте, он должен иметь фокус. Чтобы убедиться в том, что это так обрабатывать OnSetFocus таким образом, чтобы фокус всегда перемещается активным элементом при представлении получает фокус.

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

При изменении размера представления, также необходимо уведомлять активный элемент, которая была изменена прямоугольник отсечения. Для этого можно создать обработчик для `OnSize`:

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

## <a name="case-study-hiersvr-from-mfc-20"></a>Практический пример: HIERSVR из MFC 2.0

[HIERSVR](../visual-cpp-samples.md) также был включен в MFC 2.0 и реализации OLE с MFC/OLE1. Эта заметка кратко описаны шаги, по которым это приложение изначально был преобразован для использования классов MFC/OLE 2. Ряд функций были добавлены после завершения начального порта для лучшей иллюстрации классы MFC/OLE 2. Эти функции не будут рассматриваться ниже; ссылаться на сам образец Дополнительные сведения по этим дополнительным возможностям.

> [!NOTE]
> Ошибки компилятора и пошаговый процесс создания с помощью Visual C++ 2.0. Сообщения об ошибках и расположения могло измениться с Visual C++ 4.0, но основные данные остается допустимым.

## <a name="getting-it-up-and-running"></a>Обеспечение эффективности и запуск

Подход к порту образца HIERSVR на MFC/OLE — запуск с его создания и устранение ошибок очевидным компилятора, которые будут вызывать. Если взять пример HIERSVR 2.0 MFC и скомпилировать его в эту версию MFC, обнаружится, что существует множество ошибок, чтобы устранить (несмотря на то, что существует более чем с примером OCLIENT). Ниже приведено описание ошибки в том порядке, в котором они обычно расположены.

## <a name="compile-and-fix-errors"></a>Исправление ошибки компиляции и

```Output
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'
```

Эта первая ошибка указывает, много большой проблемой с `InitInstance` функцию для серверов. Инициализации, необходимые для OLE-сервер, вероятно, является одним из самых существенных изменений, которые необходимо внести в приложение MFC/OLE1 для его запуска. Лучший способ — просмотрите для OLE-сервер создается мастером приложений и изменять код соответствующим образом. Ниже приведены некоторые моменты следует учитывать:

Необходимо инициализировать библиотеки OLE, вызвав `AfxOleInit`

Вызовите SetServerInfo объекта шаблона документа для задания дескрипторы ресурсов сервера и сведения о классе среды выполнения, который нельзя задавать с помощью `CDocTemplate` конструктор.

Не показывать главное окно приложения, если/Embedding присутствует в командной строке.

Вам потребуется **GUID** для документа. Это уникальный идентификатор типа документа (128 бит). AppWizard создаст для вас — таким образом при использовании метода, описанного здесь копирования новый код из нового серверного приложения создается мастером приложений, можно просто «заполучить» идентификатор GUID из этого приложения. В противном случае можно использовать GUIDGEN. Служебная программа exe-файла в каталоге BIN.

Это необходимо для «подключиться» вашей `COleTemplateServer` объект в шаблоне документа путем вызова `COleTemplateServer::ConnectTemplate`.

Обновите реестр, при выполнении автономного приложения. Таким образом, если пользователь перемещает. EXE-файла для приложения, запустив его из нового местоположения обновит базу данных регистрации системы Windows для указания нового расположения.

После применения всех этих изменений, в зависимости от того, создается мастером приложений для `InitInstance`, `InitInstance` (и связанные с GUID) для HIERSVR должна выглядеть следующим образом:

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

Обратите внимание, что приведенный выше код ссылается на новый идентификатор ресурса, IDR_HIERSVRTYPE_SRVR_EMB. Это меню ресурса для использования при редактировании документа, которое внедрено в другом контейнере. В MFC/OLE1 пунктов меню, относящиеся к редактирования внедренного элемента были изменены в режиме реального времени. С помощью структуры аналоговое меню, при редактировании внедренного элемента вместо редактирования документа на основе файла делает гораздо проще передать различные пользовательские интерфейсы для этих двух отдельных режимов. Как вы увидите позже, это совершенно разные меню ресурс используется при редактировании внедренный объект на месте.

Чтобы создать этот ресурс, загрузить файл скрипта ресурсов в Visual C++ и скопируйте существующий ресурс меню IDR_HIERSVRTYPE. Переименуйте новый ресурс в IDR_HIERSVRTYPE_SRVR_EMB (это же соглашение об именовании, использующий мастером приложений). Затем измените «Сохранить файл» на «Файл обновления». Присвойте ему команду ID_FILE_UPDATE идентификатор. Также измените «Сохранить файл как» на «Файл сохранить копию как»; Присвойте ему команду ID_FILE_SAVE_COPY_AS идентификатор. Платформа предоставляет реализацию обе эти команды.

```Output
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers
```

Существует несколько ошибок, полученные в результате переопределение метода `OnSetData`, так как он ссылается на **OLESTATUS** типа. **OLESTATUS** был способ OLE1 возврата ошибки. Это было изменено на **HRESULT** OLE 2, несмотря на то, что MFC обычно преобразует **HRESULT** в `COleException` содержащего ошибку. В данном случае переопределение метода `OnSetData` больше не требуется, поэтому проще всего будет удалить его.

```Output
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters
```

`COleServerItem` Конструктор принимает дополнительный параметр «BOOL». Этот флаг определяет, как управление памятью осуществляется на `COleServerItem` объектов. Присвоив ему значение true, платформа обрабатывает управление памятью этих объектов — удалять их, когда они больше не нужны. Использует HIERSVR `CServerItem` (производный от `COleServerItem`) объекты как часть его собственные данные, поэтому необходимо настроить этот флаг в значение FALSE. Это позволяет определить, когда удаляется каждого элемента сервера HIERSVR.

```Output
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
```

Эти ошибки подразумевают, существуют некоторые функции «чисто виртуальные», которые не были переопределены в CServerItem. Чаще всего это вызвано тот факт, что изменилось OnDraw в списке параметров. Чтобы устранить эту ошибку, измените `CServerItem::OnDraw` следующим образом (а также объявление в svritem.h):

```cpp
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)
{
    // request from OLE to draw node
    pDC->SetMapMode(MM_TEXT); // always in pixels
    return DoDraw(pDC, CPoint(0, 0), FALSE);
}
```

Новый параметр — «rSize». Это позволяет заполнить размер рисунка, если удобно. Этот размер должен быть в **HIMETRIC**. В этом случае неудобно для заполнения это значение, поэтому платформа вызывает `OnGetExtent` для получения степени. Чтобы это работало, необходимо реализовать `OnGetExtent`:

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

В функции CServerItem::CalcNodeSize с размером элемента преобразуется в **HIMETRIC** и хранящихся в *m_rectBounds*. Недокументированный "*m_rectBounds*" членом `COleServerItem` не существует (он будет частично заменен *m_sizeExtent*, но в OLE 2 этот член имеет немного отличается от *m_rectBounds* в OLE1). Вместо того чтобы задавать **HIMETRIC** размер в переменную-член, вам придется возвращаться. Это возвращаемое значение используется в `OnGetExtent`, реализованных ранее.

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

Также переопределяет CServerItem `COleServerItem::OnGetTextData`. Эта функция в MFC/OLE является устаревшим и заменяется другого механизма. Версия MFC 3.0 примера MFC OLE [HIERSVR](../visual-cpp-samples.md) реализует эту функцию, переопределив `COleServerItem::OnRenderFileData`. Эта функция не имеет значения для этого базового порта, чтобы вы могли удалить переопределение OnGetTextData.

Существует много дополнительных ошибок svritem.cpp, которые не были обработаны. Они не являются «реальными» ошибками — только ошибки, из-за предыдущих ошибок.

```Output
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters
```

`COleServerItem::CopyToClipboard` больше не поддерживает `bIncludeNative` флаг. Собственных данных (данные записываются с функцию Serialize элемент сервера) всегда копируется, поэтому удалить первый параметр. Кроме того `CopyToClipboard` приведет к возникновению исключения при возникновении ошибки не возвращается значение FALSE. Измените код для CServerView::OnEditCopy следующим образом:

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

Несмотря на то, что существуют дополнительные ошибки, полученный в результате компиляции версии MFC 2.0 HIERSVR, чем для той же версии OCLIENT, были фактически меньшее количество изменений.

На этом этапе HIERSVR будет скомпилировать и связать и работать как OLE-сервер, но без компонента редактирования на месте, которое затем будет реализована.

## <a name="adding-visual-editing"></a>Добавление «Визуальное редактирование»

Чтобы добавить это серверное приложение «Визуальное редактирование» (или активации на месте), существует только на несколько моментов, которые необходимо обратить:

- Требуется специальное меню ресурс для использования в том случае, если элемент является активным на месте.

- Это приложение имеет панель инструментов, поэтому вам понадобится панель инструментов с набором обычный панели инструментов в соответствии с меню команд, доступных на сервере (соответствует ресурса меню, упомянутых выше).

- Вам потребуется новый класс, производный от `COleIPFrameWnd` , предоставляющий интерфейс пользователя на месте (подобно тому как программа CMainFrame, производный от `CMDIFrameWnd`, предоставляет пользовательский интерфейс MDI).

- Необходимо сообщить платформе о эти специальные ресурсы и классы.

Ресурс можно легко создать. Запустите Visual C++, скопируйте ресурса меню IDR_HIERSVRTYPE вызывается IDR_HIERSVRTYPE_SRVR_IP ресурса меню. Измените меню, чтобы остаются только всплывающие меню Edit и справки. Добавьте два разделителя групп разрядов в меню между меню «Правка» и «справка (результат будет выглядеть так: изменение &#124; &#124; справки). Дополнительные сведения о что означают эти разделители и способ слияния меню сервера и контейнера, см. в разделе [меню и ресурсы: слияние меню](../mfc/menus-and-resources-menu-merging.md).

Точечный рисунок для панели инструментов подмножества можно легко создать путем копирования из нового приложения создается мастером приложений с флажок «Server». Затем этот точечный рисунок можно импортировать в Visual C++. Не забудьте предоставить идентификатор IDR_HIERSVRTYPE_SRVR_IP растрового изображения.

Класс, производный от `COleIPFrameWnd` можно скопировать из приложения с поддержкой серверов, а также создается мастером приложений. Скопируйте оба файла IPFRAME. CPP и IPFRAME. H и добавить их в проект. Убедитесь, что `LoadBitmap` вызов связан IDR_HIERSVRTYPE_SRVR_IP растрового изображения, созданные на предыдущем шаге.

Теперь, когда создаются новые ресурсы и классы, добавьте необходимый код, чтобы среда знает об этих (она знает, что это приложение сейчас поддерживает редактирование на месте). Это делается путем добавления некоторые дополнительные параметры для `SetServerInfo` вызов в `InitInstance` функции:

```cpp
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```

Теперь все готово к запуску на месте в любом контейнере, который также поддерживает активацию на месте. Но есть один дополнительный номер ошибки, по-прежнему таится в коде. HIERSVR поддерживает контекстное меню, отображаемое, когда пользователь нажимает правую кнопку мыши. Это меню работает, когда HIERSVR полностью открыт, но не работает при редактировании внедрения по месту. Причина можно закрепить на этом одной строки кода в CServerView::OnRButtonDown:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```

Обратите внимание, что ссылка на `AfxGetApp()->m_pMainWnd`. Когда сервер находится активироваться на месте, он имеет главное окно и m_pMainWnd имеет значение, но обычно скрыты. Кроме того, это окно ссылается на *основной* окна приложения, окно области MDI, которое отображается, когда сервер находится полностью открытия и запуска автономного. Этот параметр не относится к окну активного кадра, которой при на месте активации — это блок окно производным от `COleIPFrameWnd`. Чтобы получить правильный активного окна, даже в том случае, если редактирование на месте, эту версию MFC добавляет новую функцию, `AfxGetMainWnd`. Как правило, следует использовать эту функцию вместо `AfxGetApp()->m_pMainWnd`. Этот код необходимо изменить следующим образом:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetMainWnd());
```

Теперь у вас есть OLE-сервер, как минимум на поддержку функционального активации на месте. Но по-прежнему многие функции доступны с помощью MFC/OLE 2, которые не были доступны в MFC/OLE1. Ознакомьтесь с примером HIERSVR дополнительные идеи о функциях, которые можно реализовать. Ниже перечислены некоторые функции, которые реализует HIERSVR:

- Изменение масштаба для true WYSIWYG поведение по отношению к контейнеру.

- Перетаскивания и форматом пользовательского буфера обмена.

- Прокрутка окна контейнера, как выбор изменяется.

Пример HIERSVR в MFC 3.0 также использует несколько отличных для элементов сервера. Это помогает освободить ресурсы памяти и ссылки более гибким. С помощью версии 2.0 HIERSVR каждый узел в дереве *-является* `COleServerItem`. `COleServerItem` немного издержки не является строго необходимой для каждого из этих узлов, но со значением `COleServerItem` является обязательным для каждой активной ссылки. Но в большинстве случаев очень мало активных ссылок в любой момент времени. Чтобы сделать это более эффективным, HIERSVR в эту версию MFC разделяет узел из `COleServerItem`. Он имеет оба CServerNode и `CServerItem` класса. `CServerItem` (Производный от `COleServerItem`) создает только при необходимости. После контейнера (или контейнеры) остановить с помощью этой ссылки на данном узле, CServerItem объекта, связанного с CServerNode удаляется. Такой подход является более эффективными и гибкими. Его гибкость при работе с несколькими связями выбора. Ни один из этих двух версий HIERSVR поддерживает выбор нескольких элементов, но было бы гораздо проще, чтобы добавить (и поддерживает ссылки на такие выбранные параметры) в версии MFC 3.0 HIERSVR, так как `COleServerItem` отделены от собственных данных.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
