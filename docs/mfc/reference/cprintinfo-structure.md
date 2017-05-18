---
title: "CPrintInfo-структура | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ffa72acc58e0ac1a387e67e6542abcd466be9640
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cprintinfo-structure"></a>CPrintInfo-структура
Хранит сведения о печати и предварительного задания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|Возвращает номер первой страницы печати.|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|Возвращает номер последней страницы документа.|  
|[CPrintInfo::GetMinPage](#getminpage)|Возвращает номер первой страницы документа.|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Возвращает число страниц, предшествующей первой страницы элемента DocObject печать в объединенный DocObject задания печати.|  
|[CPrintInfo::GetToPage](#gettopage)|Возвращает номер последней страницы, печать.|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|Задает номер последней страницы документа.|  
|[CPrintInfo::SetMinPage](#setminpage)|Задает номер первой страницы документа.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Содержит флаг, указывающий, следует ли продолжать цикл печати платформы.|  
|[CPrintInfo::m_bDirect](#m_bdirect)|Содержит флаг, указывающий, следует ли печатать документ напрямую (без отображения диалогового окна «Печать»).|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Содержит флаг, указывающий ли DocObject выводимого на печать документа.|  
|[CPrintInfo::m_bPreview](#m_bpreview)|Содержит флаг, указывающий, сейчас выполняется предварительный просмотр документа.|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|Указывает DocObject операции печати.|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Содержит указатель на структуру, созданные пользователем.|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Определяет число страниц в настоящее время печатается.|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Указывает номер задания, назначенный операционной системой для текущего задания печати|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Общее число страниц, отображаемых в окне предварительного просмотра; 1 или 2.|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Задает смещение определенного DocObject первой страницы в объединенный DocObject задания печати.|  
|[CPrintInfo::m_pPD](#m_ppd)|Содержит указатель на `CPrintDialog` объект, используемый для диалогового окна печати.|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Задает прямоугольник, определяющий размера страницы.|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Содержит строку форматирования для отображения номеров страниц.|  
  
## <a name="remarks"></a>Примечания  
 `CPrintInfo`представляет собой структуру и не имеет базового класса.  
  
 Платформа создает объект `CPrintInfo` каждый раз при печати или команда Предварительный выбран и удаляет его при выполнении команды.  
  
 `CPrintInfo`содержит сведения о печати в целом, такие как диапазон страниц для печати и текущее состояние задания печати, например страницы, которые в настоящее время печатается. Некоторые сведения хранятся в связанный с ним [CPrintDialog](../../mfc/reference/cprintdialog-class.md) объекта; этот объект содержит значения, введенные пользователем в диалоговом окне «Печать».  
  
 Объект `CPrintInfo` объект передается между платформы и класс представления процессе печати и используется для обмена данными между ними. Например, платформа сообщает класса представления какие страницы документа для печати путем присвоения значения `m_nCurPage` членом `CPrintInfo`; представление класса извлекает значение и выполняет фактическую печать указанную страницу.  
  
 Другим примером является случай, в котором длина документа не известна до печати. В этом случае класс представления тесты для конца документа каждый раз, когда печати страницы. По достижении границы класса представления задает `m_bContinuePrinting` членом `CPrintInfo` для **FALSE**; это информирует framework для остановки цикла печати.  
  
 `CPrintInfo`используемые функции-члены `CView` перечислены в разделе «см.» Дополнительные сведения об архитектуре печати, предоставляемых библиотеки классов Microsoft Foundation см. в разделе [окна фрейма](../../mfc/frame-windows.md) и [архитектуры документ/представление](../../mfc/document-view-architecture.md) и статьи [печати](../../mfc/printing.md) и [печати: Многостраничные документы](../../mfc/multipage-documents.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CPrintInfo`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="getfrompage"></a>CPrintInfo::GetFromPage  
 Эта функция вызывается для получения номер первой страницы для печати.  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер первой страницы для печати.  
  
### <a name="remarks"></a>Примечания  
 Это значение, указанное пользователем в диалоговом окне «Печать», и он сохраняется в `CPrintDialog` объект ссылается `m_pPD` член. Если пользователь не указал значение, по умолчанию используется первой страницы документа.  
  
##  <a name="getmaxpage"></a>CPrintInfo::GetMaxPage  
 Эта функция вызывается для извлечения номера последней страницы документа.  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер последней страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Это значение хранится в `CPrintDialog` объект ссылается `m_pPD` член.  
  
##  <a name="getminpage"></a>CPrintInfo::GetMinPage  
 Эта функция вызывается для извлечения номера первой страницы документа.  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер первой страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Это значение хранится в `CPrintDialog` объект ссылается `m_pPD` член.  
  
##  <a name="getoffsetpage"></a>CPrintInfo::GetOffsetPage  
 Эта функция вызывается для извлечения значения смещения при печати нескольких элементов DocObject DocObject клиента.  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество страниц, предшествующей первой страницы элемента DocObject печать в объединенный DocObject задания печати.  
  
### <a name="remarks"></a>Примечания  
 Это значение указывает **m_nOffsetPage** член. Первой страницы документа будут пронумерованы **m_nOffsetPage** значение + 1 при печати как DocObject с других активных документов. **M_nOffsetPage** элемент действителен только тогда, когда **m_bDocObject** значение **TRUE**.  
  
##  <a name="gettopage"></a>CPrintInfo::GetToPage  
 Эта функция вызывается для извлечения номера последней страницы для печати.  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер последней страницы для печати.  
  
### <a name="remarks"></a>Примечания  
 Это значение, указанное пользователем в диалоговом окне «Печать», и он сохраняется в `CPrintDialog` объект ссылается `m_pPD` член. Если пользователь не указал значение, по умолчанию используется последней страницы документа.  
  
##  <a name="m_bcontinueprinting"></a>CPrintInfo::m_bContinuePrinting  
 Содержит флаг, указывающий, следует ли продолжать цикл печати платформы.  
  
### <a name="remarks"></a>Примечания  
 При выполнении разбиения на страницы во время печати, следует установить этот компонент **FALSE** в переопределении `CView::OnPrepareDC` достижении конца документа. Необходимо изменить эту переменную при указании длины документа в начале задания печати с помощью `SetMaxPage` функции-члена. `m_bContinuePrinting` Элемент — это открытая переменная типа **BOOL**.  
  
##  <a name="m_bdirect"></a>CPrintInfo::m_bDirect  
 Этот элемент задает платформа **TRUE** Если диалоговое окно печати не выполняется для прямой печати. **FALSE** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Диалогового окна печати обычно пропускается при печати из оболочки или при печати выполняется с помощью идентификатора команды **ID_FILE_PRINT_DIRECT**.  
  
 Здесь обычно не изменять этот член, но если изменить его, изменить его перед вызовом [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) в переопределении [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="m_bdocobject"></a>CPrintInfo::m_bDocObject  
 Содержит флаг, указывающий ли DocObject выводимого на печать документа.  
  
### <a name="remarks"></a>Примечания  
 Члены данных `m_dwFlags` и **m_nOffsetPage** являются недопустимыми, если этот флаг не **TRUE**.  
  
##  <a name="m_bpreview"></a>CPrintInfo::m_bPreview  
 Содержит флаг, указывающий, сейчас выполняется предварительный просмотр документа.  
  
### <a name="remarks"></a>Примечания  
 Это задается платформой, в зависимости от того, что выполнена команда пользователя. Диалоговое окно «Печать» не отображается для предварительного задания. **M_bPreview** элемент — это открытая переменная типа **BOOL**.  
  
##  <a name="m_dwflags"></a>CPrintInfo::m_dwFlags  
 Содержит сочетание флагов, указав DocObject операции печати.  
  
### <a name="remarks"></a>Примечания  
 Только если данные-член **m_bDocObject** — **TRUE**.  
  
 Флаги может быть один или несколько из следующих значений:  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="m_lpuserdata"></a>CPrintInfo::m_lpUserData  
 Содержит указатель на структуру, созданные пользователем.  
  
### <a name="remarks"></a>Примечания  
 Это можно использовать для хранения данных печати, не следует сохранить в классе представления. **M_lpUserData** элемент — это открытая переменная типа **LPVOID**.  
  
##  <a name="m_ncurpage"></a>CPrintInfo::m_nCurPage  
 Содержит номер текущей страницы.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает функцию `CView::OnPrepareDC` и `CView::OnPrint` один раз для каждой страницы документа, указав другое значение для этого элемента при каждом; его значения в диапазоне от значение, возвращаемое `GetFromPage` , возвращаемый `GetToPage`. Этот элемент можно использовать в вашей переопределения `CView::OnPrepareDC` и `CView::OnPrint` для печати указанной страницы документа.  
  
 При вызове режим предварительного просмотра framework считывает значение этого элемента, чтобы определить, какие страницы документа должны просматриваться изначально. Можно задать значение этого элемента в переопределении `CView::OnPreparePrinting` для поддержания пользователя текущей позиции в документе при переходе в режим предварительного просмотра. `m_nCurPage` Элемент — это открытая переменная типа **UINT**.  
  
##  <a name="m_njobnumber"></a>CPrintInfo::m_nJobNumber  
 Указывает номер задания, назначенный операционной системой для текущего задания печати.  
  
### <a name="remarks"></a>Примечания  
 Это значение может быть **SP_ERROR** Если задание еще не выдает (то есть, если `CPrintInfo` объект вновь создан и еще не использовался для печати), или если произошла ошибка при запуске задания.  
  
##  <a name="m_nnumpreviewpages"></a>CPrintInfo::m_nNumPreviewPages  
 Содержит количество страниц, отображаемых в режиме предварительного просмотра; он может быть 1 или 2.  
  
### <a name="remarks"></a>Примечания  
 **M_nNumPreviewPages** элемент — это открытая переменная типа **UINT**.  
  
##  <a name="m_noffsetpage"></a>CPrintInfo::m_nOffsetPage  
 Содержит номер страницы перед первой страницы конкретного DocObject в объединенный DocObject задания печати.  
  
##  <a name="m_ppd"></a>CPrintInfo::m_pPD  
 Содержит указатель на `CPrintDialog` объект, используемый для отображения диалоговое окно печати задания печати.  
  
### <a name="remarks"></a>Примечания  
 `m_pPD` Член — это открытая переменная, объявленная как указатель на `CPrintDialog`.  
  
##  <a name="m_rectdraw"></a>CPrintInfo::m_rectDraw  
 Указывает область рисования можно использовать страницы в логических координатах.  
  
### <a name="remarks"></a>Примечания  
 Можно ссылаться на это в переопределении `CView::OnPrint`. Этот элемент можно использовать для отслеживания того, какая область остается доступной после печати заголовки, нижние колонтитулы и т. д. **M_rectDraw** элемент — это открытая переменная типа `CRect`.  
  
##  <a name="m_strpagedesc"></a>CPrintInfo::m_strPageDesc  
 Содержит строку форматирования, используемый для отображения номеров страниц во время предварительного просмотра; Эта строка состоит из двух подстрок, один для отображения одной страницы и один для отображения страницы дважды, каждый завершаться символом «\n».  
  
### <a name="remarks"></a>Примечания  
 Платформа использует «U-%u\n % %u\nPages страницы» как значение по умолчанию. Если требуется другой формат номера страниц, задайте строку формата в переопределении `CView::OnPreparePrinting`. **M_strPageDesc** элемент — это открытая переменная типа `CString`.  
  
##  <a name="setmaxpage"></a>CPrintInfo::SetMaxPage  
 Эта функция используется для указания номера последней страницы документа.  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>Параметры  
 *nMaxPage*  
 Номер последней страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Это значение хранится в `CPrintDialog` объект ссылается `m_pPD` член. Если длина документа известен, перед печатью, эта функция вызывается из переопределение метода `CView::OnPreparePrinting`. Если длина документа зависит от параметра, указанное пользователем в диалоговом окне «Печать», эта функция вызывается из переопределение метода `CView::OnBeginPrinting`. Если длина документа не известна до печати, используйте `m_bContinuePrinting` элемент управления печати цикла.  
  
### <a name="example"></a>Пример  
  В примере показано [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="setminpage"></a>CPrintInfo::SetMinPage  
 Эта функция используется для указания номера первой страницы документа.  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>Параметры  
 *nMinPage*  
 Номер первой страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Номера страниц обычно начинаются с 1. Это значение хранится в `CPrintDialog` объект ссылается `m_pPD` член.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)   
 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)   
 [CView::OnPrint](../../mfc/reference/cview-class.md#onprint)




