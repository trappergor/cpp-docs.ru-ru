---
title: 'TN041: Миграция MFC OLE1 на MFC OLE 2 | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78faa19263ff0ea03aac891c9be3a6114f7f9a48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041. Миграция MFC/OLE1 на MFC/OLE 2
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
## <a name="general-issues-relating-to-migration"></a>Общие вопросы, относящиеся к миграции  
 Одна из целей проектирования для классов OLE 2 2.5 MFC (и более поздние версии) было сохранить большую часть ту же архитектуру, реализованы в MFC 2.0 для поддержки OLE 1.0. В результате многие те же классы OLE в MFC 2.0 по-прежнему существует в данной версии MFC (`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`). Кроме того многие API в этих классах, одинаковы. Тем не менее OLE 2 значительно отличается от OLE 1.0, и вы можете ожидать, что некоторые сведения были изменены. Если вы знакомы с поддержкой OLE1 на MFC 2.0, вы сможете дома с поддержкой 2.0 MFC.  
  
 Если принимающий существующее приложение MFC/OLE1 и добавление функциональные возможности OLE 2, следует ознакомиться с этой заметке сначала. Эта заметка рассматриваются некоторые общие проблемы могут возникать при переносе работоспособность OLE1 на MFC/OLE 2 и затем рассматриваются проблемы, которые были выявлены во время переноса двух приложений, включенных в MFC 2.0: в примерах MFC OLE [OCLIENT](../visual-cpp-samples.md) и [HIERSVR](../visual-cpp-samples.md).  
  
## <a name="mfc-documentview-architecture-is-important"></a>Важно архитектурой документ/представление MFC  
 Если приложение не использует MFC архитектуры Document/View и вы хотите добавить в приложение поддержки OLE 2, пришло время для перемещения документов и представлений. Преимущества классов MFC OLE 2 реализуются только когда приложение использует встроенные архитектура и компоненты MFC.  
  
 Реализация сервера или контейнера без использования архитектуры MFC можно, но не рекомендуется.  
  
## <a name="use-mfc-implementation-instead-of-your-own"></a>Используйте вместо собственные реализации MFC  
 Реализация MFC «canned» классов, такие как `CToolBar`, `CStatusBar`, и `CScrollView` имеют встроенные специального кода вариантов поддержки OLE 2. Таким образом Если эти классы можно использовать в приложении будет преимущества пытается перевести их в информировании их OLE. Опять же имеется возможность «сводный your владельцем» здесь классов для этих целей, но не рекомендуется. Если необходимо реализовать аналогичные функциональные возможности, исходный код MFC предоставляет для работы с некоторыми более точно точек OLE (особенно когда дело доходит до активации на месте).  
  
## <a name="examine-the-mfc-sample-code"></a>Проверьте код MFC, образец  
 Существует ряд примеров MFC, которые включают функции OLE. Каждый из этих приложений реализует OLE из другой угол.  
  
- [HIERSVR](../visual-cpp-samples.md) предназначен главным образом для использования в качестве серверного приложения. Оно было включено в MFC 2.0 как приложение MFC/OLE1 и переносить на MFC/OLE 2 и затем дополняется таким образом, что он реализует OLE возможностей, доступных в OLE 2.  
  
- [OCLIENT](../visual-cpp-samples.md) это приложение изолированного контейнера, предназначен для демонстрации многие функции OLE с точки зрения контейнера. Он слишком был перенесен из MFC 2.0 и затем расширены для поддержки множества дополнительных функций OLE, таких как форматы буфера обмена пользовательские и ссылки на внедренные элементы.  
  
- [ФУНКЦИЙ](../visual-cpp-samples.md) это приложение реализует поддержка контейнера OLE гораздо стиле OCLIENT, за исключением того, что она делает это в структуре объектно ориентированного рисования программу. Он показывает, как можно реализовать поддержку контейнера OLE и интегрировать в существующие приложения.  
  
- [SUPERPAD](../visual-cpp-samples.md) этого приложения, а также выполняется нормально автономное приложение, также является OLE-сервер. Поддержка сервера, которое он реализует является довольно минималистский интерфейс. Особый интерес представляет использование службы OLE буфера обмена для копирования данных в буфер обмена, но использует функции, встроенные в элемент управления Windows «edit» для реализации функциональности вставки в буфер обмена. Это показывает интересные сочетание традиционного использования Windows API, а также интеграцию с новые API-интерфейсы OLE.  
  
 Дополнительные сведения об образцах приложений см. в справке» MFC образец».  
  
## <a name="case-study-oclient-from-mfc-20"></a>Практический пример: OCLIENT из MFC 2.0  
 Как было сказано выше, [OCLIENT](../visual-cpp-samples.md) был включен в MFC 2.0 и реализации OLE с MFC/OLE1. Ниже описаны действия, по которым это приложение изначально преобразован для использования классов MFC/OLE 2. Ряд функций были добавлены после завершения начального порта чтобы лучше проиллюстрировать классы MFC/OLE. Эти возможности здесь не рассматриваются. см. Образец сам Дополнительные сведения об этих дополнительных функций.  
  
> [!NOTE]
>  Ошибки компиляции и пошаговый процесс создания в Visual C++ 2.0. Сообщения об ошибках и расположения могло измениться с Visual C++ 4.0, но остается действительным, общие сведения.  
  
## <a name="getting-it-up-and-running"></a>Обеспечение эффективности и выполнение  
 — Начать с его создания и устранение ошибок компилятора очевидным, которые приведут к подходов, использованных для порта Образец OCLIENT на MFC/OLE. Если взять образец OCLIENT 2.0 MFC и скомпилировать его в данной версии MFC, можно найти, что не отсутствуют ошибки, что многие. Ниже приводится описание ошибки в порядке, в котором они имели место.  
  
## <a name="compile-and-fix-errors"></a>Исправление ошибки компиляции и  
  
```  
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters  
```  
  
 Первая ошибка проблемы `COleClientItem::Draw`. В MFC/OLE1 потратил бы несколько параметров, чем версия MFC/OLE принимает. Лишние параметры были часто не требуется и обычно NULL (как в этом примере). Эта версия MFC может автоматически определить значения для lpWBounds при CDC, которая рисуется в метафайл контроллера домена. Кроме того параметр pFormatDC нет необходимости, так как платформа построит один из «атрибута контроллера домена» основной контроллер домена, переданный. Поэтому чтобы устранить эту проблему, просто удалите два дополнительных NULL параметров вызова Draw.  
  
```  
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier  
\oclient\mainview.cpp(273) : error C2057: expected constant expression  
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
```  
  
 Ошибки выше результат из-за того, все **COleClientItem::CreateXXXX** необходимые функции в MFC/OLE1 прохождение уникальное имя для представления элемента. Это было требование базовой OLE API-интерфейса. Это не требуется в MFC/OLE 2, так как OLE 2 не использует DDE как базовый механизм взаимодействия (имя использовалось в диалогах DDE). Чтобы устранить эту проблему, можно удалить **CreateNewName** функции, а также все ссылки на него. Его можно легко определить, что каждая функция MFC/OLE ожидает в этой версии достаточно поместить курсор на вызов и нажав клавишу F1.  
  
 Еще одна область, который существенно отличается — обработка буфер обмена OLE 2. С OLE1 используемые в буфер обмена Windows API-интерфейсы взаимодействия с буфером обмена. С OLE 2 это делается с помощью другого механизма. API-интерфейсов MFC/OLE1 предполагается, что буфер обмена был открыт перед копированием `COleClientItem` объектов в буфер обмена. Это больше не требуется и приведет к сбою все операции с буфером обмена MFC/OLE. Во время редактирования кода для удаления зависимостей на **CreateNewName**, следует удалить код, который открывает и закрывает в буфер обмена Windows.  
  
```  
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier  
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function  
\oclient\mainview.cpp(344) : error C2057: expected constant expression  
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'  
```  
  
 Эти ошибки результатом **CMainView::OnInsertObject** обработчика. Обработка команд «Вставить объект» еще одна область, где изменился немного. В этом случае проще просто дополнить исходной реализации, предоставленное мастером приложений для нового приложения OLE-контейнера. На самом деле это метод, который можно применить к перенос других приложений. В MFC/OLE1, отображается диалоговое окно «Вставить объект» путем вызова **AfxOleInsertDialog** функции. В этой версии конструкцию **COleInsertObject** объекта диалогового окна и вызвать метод `DoModal`. Кроме того, новые элементы OLE создаются с **CLSID** вместо classname строки. Конечный результат должен выглядеть примерно следующим образом  
  
```  
COleInsertDialog dlg;  
if (dlg.DoModal() != IDOK)  
    return; 
 
BeginWaitCursor();

 
CRectItem* pItem = NULL;  
TRY  
{ *// First create the C++ object  
    pItem = GetDocument()->CreateItem();
ASSERT_VALID(pItem);

 *// Initialize the item from the dialog data.  
    if (!dlg.CreateItem(pItem))  
    AfxThrowMemoryException();
*// any exception will do  
    ASSERT_VALID(pItem);

 *// run the object if appropriate  
    if (dlg.GetSelectionType() == 
    COleInsertDialog::createNewItem) 
    pItem->DoVerb(OLEIVERB_SHOW,
    this);

 *// update right away  
    pItem->UpdateLink();
pItem->UpdateItemRectFromServer();

 *// set selection to newly inserted item  
    SetSelection(pItem);

 pItem->Invalidate();

}  
CATCH (CException,
    e)  
{ *// clean up item  
    if (pItem != NULL)  
    GetDocument()->DeleteItem(pItem);

 
    AfxMessageBox(IDP_FAILED_TO_CREATE);

} 
END_CATCH  
 
EndWaitCursor();
```  
  
> [!NOTE]
>  Вставка нового объекта может быть разным для приложения):  
  
 Также необходимо включить \<afxodlgs.h >, который содержит объявление **COleInsertObject** класса диалогового окна, а также другие стандартные диалоговые окна MFC.  
  
```  
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier  
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters  
```  
  
 Эти ошибки возникают из-за того, были ли изменены некоторые константы OLE1 OLE 2, хотя по замыслу они одинаковы. В этом случае **OLEVERB_PRIMARY** изменилось на `OLEIVERB_PRIMARY`. В OLE1 и OLE 2 первичный глагол обычно выполняется в контейнере при двойном щелчке на элемент.  
  
 Кроме того `DoVerb` теперь принимает дополнительный параметр — указатель на представление (`CView`*). Этот параметр используется только для реализации «Визуальное редактирование» (или активации на месте). Теперь задать этому параметру значение NULL, так как эта функция в настоящее время не реализуется.  
  
 Чтобы убедиться в том, что платформа никогда не пытается на месте активировать, нужно переопределить `COleClientItem::CanActivate` следующим образом:  
  
```  
BOOL CRectItem::CanActivate()  
{  
    return FALSE;  
}  
 
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier  
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function  
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier  
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function  
```  
  
 В MFC/OLE1 **COleClientItem::GetBounds** и **SetBounds** были использованы для запросов и область элемента управления ( **левой** и **верхней**члены всегда равны нулю). В MFC/OLE 2 это напрямую поддерживается `COleClientItem::GetExtent` и `SetExtent`, что работать с **размер** или `CSize` вместо.  
  
 Код для вашего нового SetItemRectToServer и вызовы UpdateItemRectFromServer будет выглядеть следующим образом:  
  
```  
BOOL CRectItem::UpdateItemRectFromServer()  
{  
    ASSERT(m_bTrackServerSize);

 CSize size;  
    if (!GetExtent(&size))  
    return FALSE;    // blank  
 *// map from HIMETRIC to screen coordinates  
 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.LPtoDP(&size);

 } *// just set the item size  
    if (m_rect.Size() != size)  
 { *// invalidate the old size/position  
    Invalidate();
m_rect.right = m_rect.left + size.cx;  
    m_rect.bottom = m_rect.top + size.cy; *// as well as the new size/position  
    Invalidate();

 }  
    return TRUE;  
}  
 
BOOL CRectItem::SetItemRectToServer()  
{ *// set the official bounds for the embedded item  
    CSize size = m_rect.Size();

 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.DPtoLP(&size);

 }  
    TRY 
 {  
    SetExtent(size);
*// may do a wait  
 }  
    CATCH(CException, e)  
 {  
    return FALSE;  // links will not allow SetBounds  
 }  
    END_CATCH 
    return TRUE;  
}  
 
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'  
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier  
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function  
```  
  
 В MFC/OLE1 синхронного API вызовов из контейнера сервера были *имитацию*, так как асинхронная во многих случаях OLE1. Требовалось наличие необработанных асинхронный вызов выполняется перед обработкой команды от пользователя. MFC/OLE1 предоставленный **COleClientItem::InWaitForRelease** функция это сделать. В MFC/OLE 2 это нет необходимости, чтобы можно было удалить переопределение метода OnCommand в CMainFrame все вместе.  
  
 На этом этапе OCLIENT компиляции и компоновки.  
  
## <a name="other-necessary-changes"></a>Другие необходимые изменения.  
 Существует несколько действий, которые не выполняются, будет препятствовать OCLIENT запуску, однако. Лучше устранить проблемы теперь вместо более поздней версии.  
  
 Во-первых необходимо инициализировать библиотеки OLE. Это делается путем вызова **AfxOleInit** из `InitInstance`:  
  
```  
if (!AfxOleInit())  
{  
    AfxMessageBox("Failed to initialize OLE libraries");

    return FALSE;  
}  
```  
  
 Также рекомендуется проверить для виртуальных функций для изменения списка параметров. Такие функции `COleClientItem::OnChange`, переопределенный в каждое приложение контейнера MFC/OLE. Просмотрев справки в Интернете, вы увидите, что был добавлен дополнительный «DWORD dwParam». Новый CRectItem::OnChange выглядит следующим образом:  
  
```  
void   
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)  
{  
    if (m_bTrackServerSize&& 
 !UpdateItemRectFromServer())  
 { *// Blank object  
    if (wNotification == OLE_CLOSED)  
 { *// no data received for the object - destroy it  
    ASSERT(!IsVisible());

 GetDocument()->DeleteItem(this);

    return; // no update (item is gone now)  
 }  
 }  
    if (wNotification != OLE_CLOSED)  
    Dirty();
Invalidate();
*// any change will cause a redraw  
}  
```  
  
 В MFC/OLE1 приложения контейнера производный класс документа из **COleClientDoc**. В MFC/OLE 2 этот класс был удален и заменен `COleDocument` (этой новой организации для упрощения создания контейнера и сервера приложений). Отсутствует `#define` сопоставляемого **COleClientDoc** для `COleDocument` для упрощения переноса приложений MFC/OLE1 на MFC/OLE 2, например OCLIENT. Одна из функций, не предоставляемые `COleDocument` , предоставленный компанией **COleClientDoc** — стандартная команда сообщение записей карты. Это будет сделано, серверных приложений, которые также используют `COleDocument` (не напрямую), не содержат с ними издержки, связанные с этими обработчики команд не являющиеся приложения контейнера и сервера. Необходимо добавить следующие записи в схеме сообщений CMainDoc:  
  
```  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE,
    OnUpdatePasteMenu)  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK,
    OnUpdatePasteLinkMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS,
    OnUpdateEditLinksMenu)  
ON_COMMAND(ID_OLE_EDIT_LINKS,
    COleDocument::OnEditLinks)  
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST,
    OnUpdateObjectVerbMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT,
    OnUpdateObjectVerbMenu)  
ON_COMMAND(ID_OLE_EDIT_CONVERT,
    OnEditConvert)  
```  
  
 Реализация всех этих команд выполняется в `COleDocument`, который является базовым классом для документа.  
  
 На этом этапе OCLIENT является режим работы приложения OLE-контейнера. Можно вставлять элементы любого типа (OLE1 или OLE 2). Так как не реализован необходимый код для включения активации на месте, в отдельном окне, практически как с OLE1 редактировать элементы. В следующем разделе показан необходимые изменения, чтобы включить редактирование на месте (иногда называется «Визуальное редактирование»).  
  
## <a name="adding-visual-editing"></a>Добавление «Визуального редактирования»  
 Одним из наиболее интересных возможностей OLE является активация на месте (или «Визуального редактирования»). Эта функция позволяет приложению сервер берет на себя часть контейнера пользовательский интерфейс для обеспечения более удобного интерфейса редактирования для пользователя. Для реализации встроенной активации для OCLIENT, некоторые специальные ресурсы должны быть добавлены, а также дополнительный код. В мастере приложений обычно предоставляет эти ресурсы и код — фактически, большую часть кода, здесь заимствование непосредственно из нового приложения мастером приложений с поддержкой «Контейнер».  
  
 Во-первых она необходима для добавления ресурсов меню следует использовать, если элемент, который активен на месте. Этот ресурс дополнительные меню в Visual C++ можно создать путем копирования IDR_OCLITYPE ресурсов и удалив все, кроме файлов и окно всплывающие окна. Два разделителей вставляется между файл и окно и всплывающие окна для указания Разделение групп (оно должно иметь вид: файл &#124; &#124; окна). Дополнительные сведения о значении этих разделителей и способ слияния меню сервера и контейнера в разделе «Меню и ресурсы: слияние меню» в *классы OLE 2*.  
  
 После получения этих меню, созданные необходимо платформа узнала о них. Это делается путем вызова `CDocTemplate::SetContainerInfo` шаблоном документа, перед их добавлением в список шаблонов документов в InitInstance. Новый код для регистрации шаблона документа выглядит следующим образом:  
  
```  
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE, 
    RUNTIME_CLASS(CMainDoc), 
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame  
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```   
  
 Ресурс IDR_OLECLITYPE_INPLACE — специальные ресурс на месте, созданный в Visual C++.  
  
 Для включения активации на месте, существуют некоторые особенности, которые потребуется изменить в обоих `CView` (CMainView) производный класс а также `COleClientItem` производного класса (CRectItem). Все эти переопределения предоставляются в мастере приложений, и большая часть реализации будет поступать из приложения мастером приложений по умолчанию.  
  
 На первом шаге этого порта, активация на месте отключена полностью путем переопределения `COleClientItem::CanActivate`. Это переопределение должны быть удалены, чтобы разрешить активацию на месте. Кроме того, было передано значение NULL для всех вызовов `DoVerb` (существуют две из них) из-за представления только необходимые для активации на месте. Для полной реализации встроенной активации, необходимые для передачи в правильный режим `DoVerb` вызова. Одна из этих вызовов **CMainView::OnInsertObject**:  
  
```  
pItem->DoVerb(OLEIVERB_SHOW, this);
```  
  
 Другая — в **CMainView::OnLButtonDblClk**:  
  
```  
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```  
  
 Необходимо переопределить `COleClientItem::OnGetItemPosition`. Это указывает, что сервер для размещения его окна относительно контейнера окна при активации на месте элемента. Для OCLIENT реализация прост.  
  
```  
void CRectItem::OnGetItemPosition(CRect& rPosition)  
{  
    rPosition = m_rect;  
}  
```  
  
 Большинство серверов также реализовать так называемый «на месте изменения размера.» Это позволяет окна сервера изменять размеры и перемещено, пока пользователь редактирует элемента. Контейнера должны быть включены в это действие, поскольку перемещении или изменении размера окна обычно влияет на положение и размер в рамках самого документа контейнера. Реализация OCLIENT синхронизирует внутренние обслуживается m_rect новое положение и размер прямоугольника.  
  
```  
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
  
 На этом этапе имеется достаточное количество кода, позволяющего элемент для активации по месту и для изменения размера и перемещения элемента, когда он включен, но код не позволит пользователю выйти из сеанса редактирования. Несмотря на то, что некоторые серверы будут предоставлять эту функциональность самостоятельно, обрабатывая нажмите клавишу ESC, предполагается, что контейнеры предоставляют два способа деактивации элемента: (1), щелкнув за пределами элемента и (2), нажав клавишу ESCAPE.  
  
 Нажмите клавишу ESC добавить ускоритель с Visual C++, который сопоставляется клавиша VK_ESCAPE команды, ID_CANCEL_EDIT добавляется к ресурсам. Обработчик для этой команды выглядит следующим образом:  
  
```  
// The following command handler provides the standard  
// keyboard user interface to cancel an in-place  
// editing session.void CMainView::OnCancelEdit()  
{ *// Close any in-place active item on this view.  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->Close();
ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);

}  
```  
  
 Для обработки случая, когда пользователь щелкает вне элемента, добавьте следующий код в начало **CMainView::SetSelection**:  
  
```  
if (pNewSel != m_pSelection || pNewSel == NULL)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& pActiveItem != pNewSel)  
    pActiveItem->Close();

} 
 
```  
  
 Если элемент является активным на месте, он должен иметь фокус. Чтобы убедиться в том, что это так обрабатывать OnSetFocus, чтобы фокус всегда передается в активный элемент, когда представление получает фокус.  
  
```  
// Special handling of OnSetFocus and OnSize are required   
// when an object is being edited in-place.  
void CMainView::OnSetFocus(CWnd* pOldWnd)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& 
    pActiveItem->GetItemState() == COleClientItem::activeUIState)  
 { *// need to set focus to this item if it is same view  
    CWnd* pWnd = pActiveItem->GetInPlaceWindow();
if (pWnd != NULL)  
 {  
    pWnd->SetFocus();
*// don't call the base class  
    return; 
 }  
 }  
 
    CView::OnSetFocus(pOldWnd);

} 
```  
  
 При изменении размера представления необходимо уведомить активным элементом измененного отсекающего прямоугольника. Для этого добавьте обработчик для `OnSize`:  
  
```  
void CMainView::OnSize(UINT nType,
    int cx,
    int cy)  
{  
    CView::OnSize(nType,
    cx,
    cy);

    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->SetItemRects();

} 
```  
  
## <a name="case-study-hiersvr-from-mfc-20"></a>Практический пример: HIERSVR из MFC 2.0  
 [HIERSVR](../visual-cpp-samples.md) было также включено в MFC 2.0 и реализации OLE с MFC/OLE1. Эта заметка кратко описаны шаги, по которым это приложение изначально преобразован для использования классов MFC/OLE 2. Ряд функций были добавлены после завершения начального порта чтобы лучше проиллюстрировать классы MFC/OLE 2. Эти возможности здесь не рассматриваются. см. Образец сам Дополнительные сведения об этих дополнительных функций.  
  
> [!NOTE]
>  Ошибки компиляции и пошаговый процесс создания в Visual C++ 2.0. Сообщения об ошибках и расположения могло измениться с Visual C++ 4.0, но остается действительным, общие сведения.  
  
## <a name="getting-it-up-and-running"></a>Обеспечение эффективности и выполнение  
 — Начать с его создания и устранение ошибок компилятора очевидным, которые приведут к подходов, использованных для порта образца HIERSVR на MFC/OLE. Если взять образец HIERSVR 2.0 MFC и скомпилировать его в данной версии MFC, можно найти, что не отсутствуют многие ошибки, (несмотря на то, что существует более чем с образцом OCLIENT). В том порядке, в котором они обычно возникают ошибки описаны ниже.  
  
## <a name="compile-and-fix-errors"></a>Исправление ошибки компиляции и  
  
```  
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'  
```  
  
 Эта первая ошибка указывает, гораздо больше проблема с `InitInstance` функции для серверов. Для OLE-сервер требуется инициализация, скорее всего, является одним из крупнейших изменения, которые необходимо внести в приложение MFC/OLE1 для его запуска. Лучший способ — изучите создается мастером приложений для OLE-сервер, измените код соответствующим образом. Ниже приведены некоторые моменты, которые следует учитывать:  
  
 Необходимо инициализировать библиотеки OLE, вызвав **AfxOleInit**  
  
 Вызвать SetServerInfo объекта шаблона документа дескрипторы ресурсов сервера и сведения о классе среды выполнения, которые нельзя задать с помощью `CDocTemplate` конструктор.  
  
 Больше не показывать главное окно приложения, при наличии в командной строке параметры/Embedding.  
  
 Вам потребуется **GUID** документа. Это уникальный идентификатор типа документа (128 бит). Мастер приложений создаст для вас, таким образом при использовании метода, описанного здесь копирования нового кода из нового серверного приложения создается мастером приложений, вы просто «крадет» GUID из этого приложения. В противном случае можно использовать GUIDGEN. Программа exe-ФАЙЛ в каталог BIN.  
  
 Это необходимо для «подключиться» ваш `COleTemplateServer` объект в шаблоне документа путем вызова `COleTemplateServer::ConnectTemplate`.  
  
 При запуске изолированного приложения, обновите реестр. Таким образом, если пользователь перемещает указатель. EXE-файла для приложения, запуская его его в новом расположении обновит регистрации системной базы данных Windows для указания нового расположения.  
  
 После применения всех этих изменений, в зависимости от того, создается мастером приложений для `InitInstance`, `InitInstance` (и связанные с GUID) для HIERSVR следует следующим образом:  
  
```  
// this is the GUID for HIERSVR documents  
static const GUID BASED_CODE clsid = 
 { 0xA0A16360L,
    0xC19B,
    0x101A, { 0x8C,
    0xE5,
    0x00,
    0xDD,
    0x01,
    0x11,
    0x3F,
    0x12 } };  
 
/////////////////////////////////////////////////////////////////////////////  
// COLEServerApp initialization  
 
BOOL COLEServerApp::InitInstance()  
{ *// OLE 2 initialization  
    if (!AfxOleInit())  
 {  
    AfxMessageBox("Initialization of the OLE failed!");

    return FALSE;  
 }  
 *// Standard initialization  
    LoadStdProfileSettings();

// Load standard INI file options   
 *// Register document templates  
    CDocTemplate* pDocTemplate;  
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,  
    RUNTIME_CLASS(CServerDoc), 
    RUNTIME_CLASS(CMDIChildWnd), 
    RUNTIME_CLASS(CServerView));

 pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);

    AddDocTemplate(pDocTemplate);

 *// create main MDI Frame window  
    CMainFrame* pMainFrame = new CMainFrame;  
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))  
    return FALSE;  
    m_pMainWnd = pMainFrame;  
 
    SetDialogBkColor();
*// gray look  
 *// enable file manager drag/drop and DDE Execute open  
    m_pMainWnd->DragAcceptFiles();
EnableShellOpen();

 
    m_server.ConnectTemplate(clsid,
    pDocTemplate,
    FALSE);

    COleTemplateServer::RegisterAll();

 *// try to launch as an OLE server  
    if (RunEmbedded())  
 { *// "short-circuit" initialization -- run as server!  
    return TRUE;  
 }  
    m_server.UpdateRegistry();
RegisterShellFileTypes();

 *// not run as OLE server,
    so show the main window  
    if (m_lpCmdLine[0] == '\0')  
 { *// create a new (empty) document  
    OnFileNew();

 }  
    else 
 { *// open an existing document  
    OpenDocumentFile(m_lpCmdLine);

 }  
 
    pMainFrame->ShowWindow(m_nCmdShow);

 pMainFrame->UpdateWindow();

 
    return TRUE;  
}  
```  
  
 Обратите внимание, что приведенный выше код ссылается на новый идентификатор ресурса IDR_HIERSVRTYPE_SRVR_EMB. Это меню ресурса для использования при редактировании документа, внедренных в другой контейнер. В MFC/OLE1 пунктов меню, относящиеся к редактирования внедренного элемента были изменены на ходу. С помощью структуры совершенно в другом меню, при редактировании внедренного элемента вместо редактирования документа на основе файла он значительно упрощает для предоставления разных пользовательских интерфейсов для этих двух отдельных режимов. Как вы увидите позже, ресурс меню совершенно разные используется при редактировании внедренный объект на месте.  
  
 Чтобы создать этот ресурс, загрузить файл скрипта ресурсов в Visual C++ и скопируйте существующий ресурс меню IDR_HIERSVRTYPE. Переименуйте новый ресурс в IDR_HIERSVRTYPE_SRVR_EMB (это же соглашение об именовании, использующий мастером приложений). Далее измените «Сохранение файла» на «Файл обновления». Присвойте ему идентификатор команды **ID_FILE_UPDATE**. Также измените «Сохранить как» для «Сохранить копию как»; Присвойте ему идентификатор команды **ID_FILE_SAVE_COPY_AS**. Платформа предоставляет реализации обоих этих команд.  
  
```  
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations  
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers  
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'  
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'  
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers  
```  
  
 Существует ряд ошибки, возникающие в результате переопределение метода `OnSetData`, так как он ссылается на **OLESTATUS** типа. **OLESTATUS** был способ OLE1 возврата ошибки. Это было изменено на `HRESULT` OLE 2, несмотря на то, что обычно преобразует MFC `HRESULT` в `COleException` с ошибкой. В данном случае переопределение метода `OnSetData` больше не требуется, поэтому проще всего будет удалить его.  
  
```  
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters  
```  
  
 `COleServerItem` Конструктор принимает дополнительный параметр «BOOL». Этот флаг определяет, как управление памятью осуществляется на `COleServerItem` объектов. Присвойте ему значение TRUE, платформа обрабатывает управление памятью этих объектов — удалять их, когда они больше не требуется. Использует HIERSVR **CServerItem** (производный от `COleServerItem`) объектов в рамках собственные данные, поэтому этот флажок будет установлен в значение FALSE. Это позволяет определить, когда удаляется каждый элемент сервера HIERSVR.  
  
```  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
```  
  
 Эти ошибки подразумевают, существуют некоторые «чистых виртуальных» функций, которые не были переопределены в CServerItem. Скорее всего это вызвано факт изменения OnDraw в списке параметров. Чтобы устранить эту ошибку, измените **CServerItem::OnDraw** следующим образом (а также объявление в svritem.h):  
  
```  
BOOL CServerItem::OnDraw(CDC* pDC,
    CSize& rSize)  
{ *// request from OLE to draw node  
    pDC->SetMapMode(MM_TEXT);

// always in pixels  
    return DoDraw(pDC,
    CPoint(0,
    0),
    FALSE);

}  
```  
  
 Новый параметр — «rSize». Это позволяет заполнить размеры рисунка, если удобно. Этот размер должен быть в **HIMETRIC**. В этом случае неудобно для заполнения это значение, поэтому платформа вызывает `OnGetExtent` для получения экстента. Чтобы это работало, необходимо реализовать `OnGetExtent`:  
  
```  
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect,
    CSize& rSize)  
{  
    if (dwDrawAspect != DVASPECT_CONTENT)  
    return COleServerItem::OnGetExtent(dwDrawAspect,
    rSize);

 
    rSize = CalcNodeSize();
return TRUE;  
}  
 
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier  
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type  
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'  
```  
  
 В функции CServerItem::CalcNodeSize размер элемента преобразуется в **HIMETRIC** и хранятся в **m_rectBounds**. Недокументированный "**m_rectBounds**" членом `COleServerItem` не существует (он будет частично заменен `m_sizeExtent`, но OLE 2 этот член использует немного отличается от **m_rectBounds**делалось OLE1). Вместо параметра **HIMETRIC** размер в переменную-член, он будет возвращать. Это возвращаемое значение используется в `OnGetExtent`, реализованных ранее.  
  
```  
CSize CServerItem::CalcNodeSize()  
{  
    CClientDC dcScreen(NULL);

 
    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,  
    m_strDescription.GetLength());

 m_sizeNode += CSize(CX_INSET* 2,
    CY_INSET* 2);

 *// set suggested HIMETRIC size  
    CSize size(m_sizeNode.cx,
    m_sizeNode.cy);

    dcScreen.SetMapMode(MM_HIMETRIC);

 dcScreen.DPtoLP(&size);

    return size;  
}  
```  
  
 Также переопределяет CServerItem **COleServerItem::OnGetTextData**. Эта функция в MFC/OLE является устаревшим и заменяется другого механизма. Версия образца MFC OLE MFC 3.0 [HIERSVR](../visual-cpp-samples.md) реализует данную функциональность путем переопределения `COleServerItem::OnRenderFileData`. Эта функция не имеет значения для этого базового порта, чтобы можно было удалить OnGetTextData переопределение.  
  
 Существует большое количество несколько ошибок в svritem.cpp, которые не были обработаны. Они не являются «real» ошибок — только ошибки, вызванные предыдущих ошибок.  
  
```  
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters  
```  
  
 `COleServerItem::CopyToClipboard` больше не поддерживает флаг «bIncludeNative». Собственные данные (данные, написанном функция сериализации элемента сервера) всегда копировать, чтобы удалить первый параметр. Кроме того `CopyToClipboard` вызовет исключение при возникновении ошибки вместо возвращения FALSE. Измените код для CServerView::OnEditCopy следующим образом.  
  
```  
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
  
 Несмотря на то, что произошли дополнительные ошибки, возникающие в результате компиляции версии MFC 2.0 HIERSVR, чем для одной и той же версии OCLIENT, были фактически меньшее количество изменений.  
  
 На этом этапе HIERSVR будет выполняться компиляция и связывание и функционировать как OLE-сервер, но без компонентом редактирования по месту, который будет реализован рядом.  
  
## <a name="adding-visual-editing"></a>Добавление «Визуального редактирования»  
 Чтобы добавить это серверное приложение «Визуальное редактирование» (или активации на месте), существует только некоторые моменты, которые необходимо соблюдать осторожность из:  
  
-   Требуется специальное меню ресурса для использования в том случае, если элемент является активным на месте.  
  
-   Данное приложение имеет панель инструментов, поэтому вам понадобится только подмножество обычных инструментов, чтобы соответствовать меню команд, доступных на сервере (соответствует ресурс меню, упомянутых выше) на панели инструментов.  
  
-   Требуется новый класс, производный от `COleIPFrameWnd` , обеспечивающий интерфейс пользователя на месте (как CMainFrame, производный от `CMDIFrameWnd`, предоставляет пользовательский интерфейс MDI).  
  
-   Необходимо сообщить платформе о такие специальные ресурсы и классы.  
  
 Этот ресурс можно легко создать. Запустите Visual C++, скопируйте ресурс меню IDR_HIERSVRTYPE вызывается IDR_HIERSVRTYPE_SRVR_IP ресурс меню. Измените меню, чтобы оставить только изменить и Справка меню всплывающие окна. Добавьте два разделителя меню между меню «Правка» и «Help (оно должно иметь вид: изменение &#124; &#124; справки). Дополнительные сведения о значении этих разделителей и способ слияния меню сервера и контейнера, в разделе «Меню и ресурсы: слияние меню» в *классы OLE 2*.  
  
 Точечный рисунок для панели инструментов подмножества можно легко создать путем копирования из нового приложения создается мастером приложений с включен параметр «Server». Этот рисунок может быть импортирован в Visual C++. Не забудьте предоставить идентификатор IDR_HIERSVRTYPE_SRVR_IP растрового изображения.  
  
 Класс, производный от `COleIPFrameWnd` можно скопировать из приложения с поддержкой сервера также создается мастером приложений. Скопируйте оба файла IPFRAME. CPP и IPFRAME. H и добавить их в проект. Убедитесь, что `LoadBitmap` вызов связан IDR_HIERSVRTYPE_SRVR_IP растрового изображения, созданные на предыдущем шаге.  
  
 Теперь, когда создаются новые ресурсы и классы, добавьте необходимый код, чтобы платформа знает об этих (и знает, что это приложение теперь поддерживает редактирования по месту). Это делается путем добавления некоторые дополнительные параметры для `SetServerInfo` вызов в `InitInstance` функции:  
  
```  
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,  
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```  
  
 Теперь все готово для запуска на месте в любой контейнер, также поддерживает активацию на месте. Однако имеется один незначительная ошибка, по-прежнему памяти в коде. HIERSVR поддерживает контекстного меню, отображаемый при нажатии правой кнопки мыши. Это меню работает при HIERSVR полностью открытыми, но не работает при редактировании внедрения месте. Причина может закреплены, чтобы эта строка кода в CServerView::OnRButtonDown:  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```  
  
 Обратите внимание, ссылку на **AfxGetApp() -> m_pMainWnd**. При активации на месте сервера имеет главное окно и задать m_pMainWnd, но обычно он невидим. Кроме того, это окно ссылается на *основной* окна приложения окно области MDI, которое отображается, если сервер не полностью открыть или запустить автономный. Он не ссылается на активный фрейм окна — при на месте активировать это фрейма окна производным от `COleIPFrameWnd`. Чтобы получить правильный активного окна даже в том случае, если внутреннее соединение, эта версия MFC добавляет новую функцию `AfxGetMainWnd`. Как правило, следует использовать эту функцию вместо **AfxGetApp() -> m_pMainWnd**. Этот код необходимо изменить следующим образом:  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetMainWnd());
```  
  
 Теперь у вас OLE-сервер, как минимум на поддержку работы активации на месте. Но используются по-прежнему множество функций с MFC/OLE 2, которые не были доступны в MFC/OLE1. См. Образец HIERSVR дополнительные идеи на компоненты, которые может потребоваться реализовать. Ниже перечислены некоторые возможности, реализуемые HIERSVR.  
  
-   Изменение масштаба для true WYSISYG поведение по отношению к контейнеру.  
  
-   Перетащите / удалять и форматом пользовательского буфера обмена.  
  
-   Прокрутка окна контейнера, как выбор изменяется.  
  
 Образец HIERSVR в MFC 3.0 также использует немного другой макет для элементов сервера. Это помогает освободить ресурсы памяти и делает более гибкие ссылки. В версии 2.0 HIERSVR каждый узел в дереве *— a* `COleServerItem`. `COleServerItem` вызывает снижение немного больше, чем является обязательным для каждого из этих узлов, но `COleServerItem` является обязательным для каждой активной ссылки. Однако в большинстве случаев очень небольшое число активных ссылок в любой момент времени. Чтобы сделать это более эффективно, HIERSVR в этой версии MFC разделяет узел из `COleServerItem`. Он имеет оба CServerNode и **CServerItem** класса. **CServerItem** (производный от `COleServerItem`) создает только при необходимости. Контейнер (или контейнеры) прекратить использование этой ссылки на данном узле, CServerItem объекта, связанного с CServerNode удаляется. Такой подход является более эффективны и более гибкие. Входящий гибкость при работе с несколькими ссылками выбора. Ни один из этих двух версий HIERSVR поддерживает выбор нескольких элементов, но он будет гораздо проще добавить (и поддерживает ссылки на такие выбранные параметры) с версией MFC 3.0 HIERSVR, так как `COleServerItem` отделяется от собственных данных.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

