---
title: Cprintinfo-структура
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 259dfd6808a5e975fb22d11d0a8c569237733eae
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524525"
---
# <a name="cprintinfo-structure"></a>Cprintinfo-структура

Хранит сведения о задании печати или просмотра перед печатью.

## <a name="syntax"></a>Синтаксис

```
struct CPrintInfo
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPrintInfo::GetFromPage](#getfrompage)|Возвращает номер первой печатаемой страницы.|
|[CPrintInfo::GetMaxPage](#getmaxpage)|Возвращает номер последней страницы документа.|
|[CPrintInfo::GetMinPage](#getminpage)|Возвращает номер первой страницы документа.|
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Возвращает число страниц, предшествующие первой странице элемент DocObject печатаемой в объединенный DocObject задания печати.|
|[CPrintInfo::GetToPage](#gettopage)|Возвращает номер последней печатаемой страницы.|
|[CPrintInfo::SetMaxPage](#setmaxpage)|Задает номер последней страницы документа.|
|[CPrintInfo::SetMinPage](#setminpage)|Задает номер первой страницы документа.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Содержит флаг, указывающий, следует ли продолжать печати цикла платформы.|
|[CPrintInfo::m_bDirect](#m_bdirect)|Содержит флаг, указывающий, печатается ли документ напрямую (без отображения диалогового окна «Печать»).|
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Содержит флаг, указывающий, является ли документ печатаемой DocObject.|
|[CPrintInfo::m_bPreview](#m_bpreview)|Содержит флаг, указывающий сейчас выполняется предварительный просмотр документа.|
|[CPrintInfo::m_dwFlags](#m_dwflags)|Указывает DocObject операции печати.|
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Содержит указатель на структуру, созданные пользователем.|
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Определяет номер страницы, в настоящий момент печатается.|
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Указывает номер задания, назначенный операционной системой для текущего задания печати|
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Общее число страниц, отображаемых в окне предварительного просмотра; 1 или 2.|
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Задает смещение первой страницы определенного DocObject в объединенный DocObject задания печати.|
|[CPrintInfo::m_pPD](#m_ppd)|Содержит указатель на `CPrintDialog` объект, используемый для диалогового окна печати.|
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Задает прямоугольник, определяющий текущий полезная область страницы.|
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Содержит строку форматирования для отображения номера страницы.|

## <a name="remarks"></a>Примечания

`CPrintInfo` представляет собой структуру и не имеет базового класса.

Платформа создает объект `CPrintInfo` каждый раз при печати или команда Предварительный просмотр печати выбирается и удаляет его при выполнении команды.

`CPrintInfo` содержит сведения о печати в целом, такие как диапазон страниц для печати и текущее состояние задания печати, например страницы, в настоящий момент печатается. Некоторые сведения хранятся в связанный [CPrintDialog](../../mfc/reference/cprintdialog-class.md) объекта; этот объект содержит значения, введенные пользователем в диалоговом окне печати.

Объект `CPrintInfo` объект передается между платформой и классе представления, в процессе печати и используется для обмена данными между ними. Например, платформа сообщает класс представления страницу документа должны быть напечатаны путем присвоения значения для `m_nCurPage` членом `CPrintInfo`; представление класс возвращает значение и выполняет фактическую печать указанную страницу.

Другим примером является случай, в котором длина документа не известна до печати. В этом случае класс представления тесты для конца документа каждый раз при печати страницы. При достижении окончания, задает класс представления `m_bContinuePrinting` членом `CPrintInfo` значение FALSE; это значение сообщает структурой для остановки цикла печати.

`CPrintInfo` используемые функции-члены `CView` перечисленные в разделе «см. также.» Дополнительные сведения об архитектуре печати, предоставляемый библиотекой классов Microsoft Foundation см. в разделе [фрейма Windows](../../mfc/frame-windows.md) и [архитектуры Document/View](../../mfc/document-view-architecture.md) и статьях [ Печать](../../mfc/printing.md) и [печати: Многостраничные документы](../../mfc/multipage-documents.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CPrintInfo`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage

Вызывайте эту функцию, чтобы получить номер первой страницы для печати.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер первой страницы для печати.

### <a name="remarks"></a>Примечания

Это значение, указанное пользователем в диалоговом окне печати, и он хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член. Если пользователь не указал значение, по умолчанию используется первой страницы документа.

##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage

Вызывайте эту функцию, чтобы получить номер последней страницы документа.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер последней страницы документа.

### <a name="remarks"></a>Примечания

Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член.

##  <a name="getminpage"></a>  CPrintInfo::GetMinPage

Вызывайте эту функцию, чтобы получить номер первой страницы документа.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер первой страницы документа.

### <a name="remarks"></a>Примечания

Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член.

##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage

Вызывайте эту функцию для извлечения значения смещения при печати нескольких элементов DocObject из клиента DocObject.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество страниц, предшествующие первой странице элемент DocObject печатаемой в объединенный DocObject задания печати.

### <a name="remarks"></a>Примечания

Это значение указывается с `m_nOffsetPage` член. Первая страница документа будут пронумерованы `m_nOffsetPage` значение + 1 при печати как DocObject с других активных документов. `m_nOffsetPage` Член является допустимым только если `m_bDocObject` имеет значение TRUE.

##  <a name="gettopage"></a>  CPrintInfo::GetToPage

Вызывайте эту функцию, чтобы получить номер последней страницы для печати.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер последней страницы для печати.

### <a name="remarks"></a>Примечания

Это значение, указанное пользователем в диалоговом окне печати, и он хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член. Если пользователь не указал значение, по умолчанию используется последняя страница документа.

##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting

Содержит флаг, указывающий, следует ли продолжать печати цикла платформы.

### <a name="remarks"></a>Примечания

Если вы выполняете разбиение на страницы во время печати, этот член можно задать значение FALSE в переопределении `CView::OnPrepareDC` достижении конца документа. Необходимо изменить эту переменную в том случае, если вы указали длину документа в начале задания печати с помощью `SetMaxPage` функция-член. `m_bContinuePrinting` Член — это открытая переменная типа BOOL.

##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect

Платформа присваивает этот член значение TRUE, если диалоговое окно «Печать», пропускается для прямой печати; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

Диалоговое окно печати обычно пропускается при печати из оболочки или после печати с помощью команды ID_FILE_PRINT_DIRECT идентификатор.

Вы обычно не изменяйте этот элемент, но если изменить его, изменить его перед вызовом [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) в переопределении [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject

Содержит флаг, указывающий, является ли документ печатаемой DocObject.

### <a name="remarks"></a>Примечания

Данные-члены `m_dwFlags` и `m_nOffsetPage` являются недопустимыми, если этот флаг имеет значение TRUE.

##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview

Содержит флаг, указывающий сейчас выполняется предварительный просмотр документа.

### <a name="remarks"></a>Примечания

Этот параметр задается в зависимости от того, что выполнена команда пользователь платформой. Диалоговое окно «Печать» не отображается для предварительного задания. `m_bPreview` Член — это открытая переменная типа BOOL.

##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags

Содержит сочетание флагов, определяющих операции печати DocObject.

### <a name="remarks"></a>Примечания

Действительно, только если данные-член `m_bDocObject` имеет значение TRUE.

Флаги могут иметь одно или несколько из следующих значений:

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData

Содержит указатель на структуру, созданные пользователем.

### <a name="remarks"></a>Примечания

Это можно использовать для хранения данных, вы не хотите хранить в классе представления, относящихся к печати. `m_lpUserData` Член — это открытая переменная типа LPVOID.

##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage

Содержит номер текущей страницы.

### <a name="remarks"></a>Примечания

Платформа вызывает `CView::OnPrepareDC` и `CView::OnPrint` один раз для каждой страницы документа, указав другое значение для этого элемента каждый раз; его значения в диапазоне от значения, возвращенного `GetFromPage` , возвращенный `GetToPage`. Этот элемент можно использовать в вашей переопределения `CView::OnPrepareDC` и `CView::OnPrint` печать указанного страницы документа.

При вызове режим предварительного просмотра framework считывает значение этого члена, чтобы определить, какая страница документа должны просматриваться изначально. Можно задать значение этого элемента в переопределении `CView::OnPreparePrinting` для поддержания пользователя текущей позиции в документе при переходе в режим предварительного просмотра. `m_nCurPage` Член — это открытая переменная типа целое число без знака.

##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber

Указывает номер задания, назначенный операционной системой для текущего задания печати.

### <a name="remarks"></a>Примечания

Это значение может быть SP_ERROR, если задание еще не выдает (то есть, в том случае, если `CPrintInfo` только что созданный объект и еще не использовался для печати), или если произошла ошибка при запуске задания.

##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages

Содержит номер страницы, отображаемые в режиме предварительного просмотра; он может быть 1 или 2.

### <a name="remarks"></a>Примечания

`m_nNumPreviewPages` Член — это открытая переменная типа целое число без знака.

##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage

Содержит номер страницы, перед первой странице определенного DocObject в объединенный DocObject задания печати.

##  <a name="m_ppd"></a>  CPrintInfo::m_pPD

Содержит указатель на `CPrintDialog` объект, используемый для отображения диалоговое окно печати для задания печати.

### <a name="remarks"></a>Примечания

`m_pPD` Член — это открытая переменная, объявленная как указатель на `CPrintDialog`.

##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw

Указывает области рисования можно использовать страницы в логических координатах.

### <a name="remarks"></a>Примечания

Вы можете указывать его в переопределении `CView::OnPrint`. Этот элемент можно использовать для отслеживания какая область остается доступной после печати заголовки, нижние колонтитулы и т. д. `m_rectDraw` Член — это открытая переменная типа `CRect`.

##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc

Содержит строку формата, используемый для отображения номера страниц во время предварительного просмотра печати; Эта строка состоит из двумя подстроками, один для отображения одной страницы и один для отображения страницы double, каждый завершаются символом «\n».

### <a name="remarks"></a>Примечания

Инфраструктура использует «U-%u\n % %u\nPages страницы» как значение по умолчанию. Если требуется другой формат для номеров страниц, укажите строку формата в переопределении `CView::OnPreparePrinting`. `m_strPageDesc` Член — это открытая переменная типа `CString`.

##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage

Вызывайте эту функцию, чтобы указать номер последней страницы документа.

```
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>Параметры

*nMaxPage*<br/>
Номер последней страницы документа.

### <a name="remarks"></a>Примечания

Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член. Если длина документа известен, перед печатью, вызов этой функции из переопределенный `CView::OnPreparePrinting`. Если длина документа зависит от настроек, заданных с пользователем в диалоговом окне печати, эта функция вызывается из переопределенный `CView::OnBeginPrinting`. Если длина документа не известна до печати, используйте `m_bContinuePrinting` член для управления циклом печати.

### <a name="example"></a>Пример

  См. в примере [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

##  <a name="setminpage"></a>  CPrintInfo::SetMinPage

Вызывайте эту функцию, чтобы указать номер первой страницы документа.

```
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>Параметры

*nMinPage*<br/>
Номер первой страницы документа.

### <a name="remarks"></a>Примечания

Номера страниц обычно начинаются с 1. Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член.

## <a name="see-also"></a>См. также

[Пример MFC DIBLOOK](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView::OnPrint](../../mfc/reference/cview-class.md#onprint)

