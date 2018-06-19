---
title: CPrintInfo-структура | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1da952e14158ab92d888a703aa8451c0ca39406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376591"
---
# <a name="cprintinfo-structure"></a>CPrintInfo-структура
Хранит сведения о задании печати или предварительного просмотра перед печатью.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|Возвращает номер первой страницы, печать файла.|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|Возвращает номер последней страницы документа.|  
|[CPrintInfo::GetMinPage](#getminpage)|Возвращает номер первой страницы документа.|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Возвращает число страниц, предшествующий элемент DocObject печатаемой в объединенный DocObject задания печати на первой странице.|  
|[CPrintInfo::GetToPage](#gettopage)|Возвращает номер последней страницы, печать файла.|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|Задает номер последней страницы документа.|  
|[CPrintInfo::SetMinPage](#setminpage)|Задает номер первой страницы документа.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Содержит флаг, указывающий, следует ли продолжать печати цикла платформу.|  
|[CPrintInfo::m_bDirect](#m_bdirect)|Содержит флаг, указывающий, следует ли печатать документ напрямую (без отображения диалогового окна «Печать»).|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Содержит флаг, указывающий, является ли печатаемый документ DocObject.|  
|[CPrintInfo::m_bPreview](#m_bpreview)|Содержит флаг, указывающий, является ли документ при предварительном просмотре.|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|Указывает DocObject операций печати.|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Содержит указатель на структуру, созданные пользователем.|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Общее число страниц, которые в настоящее время печатается.|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Указывает номер задания, назначенный операционной системой для текущего задания печати|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Общее число страниц, отображаемых в окне предварительного просмотра; 1 или 2.|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Задает смещение определенного DocObject первой страницы в объединенный DocObject задания печати.|  
|[CPrintInfo::m_pPD](#m_ppd)|Содержит указатель на `CPrintDialog` объект, используемый для диалогового окна печати.|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Указывает прямоугольник, определяющий область текущего размера страницы.|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Содержит строку формата для отображения номера страницы.|  
  
## <a name="remarks"></a>Примечания  
 `CPrintInfo` Структура и не имеет базового класса.  
  
 Платформа создает объект `CPrintInfo` каждый раз при печати или предварительного просмотра перед печатью команда выбирается и удаляет его при выполнении команды.  
  
 `CPrintInfo` содержит сведения о печати в целом, такие как диапазон страниц для печати и текущее состояние задания печати, например страницы, которые в настоящее время печатается. Некоторые сведения хранятся в связанную с ним [CPrintDialog](../../mfc/reference/cprintdialog-class.md) объекта; этот объект содержит значения, введенные пользователем в диалоговом окне «Печать».  
  
 Объект `CPrintInfo` объект передается между .NET framework и классе представления процессе печати и используется для обмена данными между ними. Например, платформа сообщает класс представления, какие страницы документа для печати путем присвоения значения `m_nCurPage` членом `CPrintInfo`; представление класса возвращает значение и выполняет фактическую печать указанную страницу.  
  
 Другой пример — случай, в котором длина документа не известна до печати. В этом случае класс представления тестов для конца документа каждый раз, когда печати страницы. По достижении конца задает класс представления `m_bContinuePrinting` членом `CPrintInfo` для **FALSE**; это позволяет сообщить платформе для остановки цикла печати.  
  
 `CPrintInfo` используемые функции-члены `CView` перечисленных в разделе «см.» Дополнительные сведения об архитектуре печати, предоставляемые библиотекой классов Microsoft Foundation см. в разделе [фреймов](../../mfc/frame-windows.md) и [архитектуры Document/View](../../mfc/document-view-architecture.md) и статьи [ Печать](../../mfc/printing.md) и [печати: Многостраничные документы](../../mfc/multipage-documents.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CPrintInfo`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage  
 Вызывайте эту функцию для извлечения номера первой страницы для печати.  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер первой страницы для печати.  
  
### <a name="remarks"></a>Примечания  
 Это значение, указанное пользователем в диалоговом окне «Печать», и он хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член. Если пользователь не указал значение, по умолчанию используется первой страницы документа.  
  
##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage  
 Вызывайте эту функцию для извлечения номера последней страницы документа.  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер последней страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член.  
  
##  <a name="getminpage"></a>  CPrintInfo::GetMinPage  
 Вызывайте эту функцию для извлечения номера первой страницы документа.  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер первой страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член.  
  
##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage  
 Вызывайте эту функцию для извлечения значения смещения при печати нескольких элементов DocObject DocObject клиента.  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество страниц, предшествующий элемент DocObject печатаемой в объединенный DocObject задания печати на первой странице.  
  
### <a name="remarks"></a>Примечания  
 Это значение ссылается **m_nOffsetPage** член. Первой страницы документа будут пронумерованы **m_nOffsetPage** значение + 1 при печати как DocObject с других активных документов. **M_nOffsetPage** элемент действителен только тогда, когда **m_bDocObject** значение **TRUE**.  
  
##  <a name="gettopage"></a>  CPrintInfo::GetToPage  
 Вызывайте эту функцию для извлечения номера последней страницы для печати.  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер последней страницы для печати.  
  
### <a name="remarks"></a>Примечания  
 Это значение, указанное пользователем в диалоговом окне «Печать», и он хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член. Если пользователь не указал значение, значение по умолчанию — последней страницы документа.  
  
##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting  
 Содержит флаг, указывающий, следует ли продолжать печати цикла платформу.  
  
### <a name="remarks"></a>Примечания  
 При выполнении разбиения на страницы во время печати можно задать этот член **FALSE** в переопределении `CView::OnPrepareDC` достижении конца документа. Необходимо изменить эту переменную, если вы указали длину документа в начале задания печати с помощью `SetMaxPage` функции-члена. `m_bContinuePrinting` Элемента — это открытая переменная типа **BOOL**.  
  
##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect  
 Этот элемент задает платформу **TRUE** Если диалоговое окно Печать не выполняется для прямой печати. **FALSE** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Диалоговое окно печати обычно пропускаются при печати из оболочки или после завершения печати с помощью идентификатора команды **ID_FILE_PRINT_DIRECT**.  
  
 Вы обычно не изменяйте этот элемент, но если изменить его, измените его, прежде чем вызов [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) в переопределении [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject  
 Содержит флаг, указывающий, является ли печатаемый документ DocObject.  
  
### <a name="remarks"></a>Примечания  
 Члены данных `m_dwFlags` и **m_nOffsetPage** являются недопустимыми, если этот флаг не **TRUE**.  
  
##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview  
 Содержит флаг, указывающий, является ли документ при предварительном просмотре.  
  
### <a name="remarks"></a>Примечания  
 Этот параметр задается платформой, в зависимости от того, что выполнена команда пользователя. Диалоговое окно «Печать» не отображается для задания предварительного просмотра перед печатью. **M_bPreview** элемента — это открытая переменная типа **BOOL**.  
  
##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags  
 Содержит комбинацию флаги, определяющие DocObject операций печати.  
  
### <a name="remarks"></a>Примечания  
 Только если элемент данных **m_bDocObject** — **TRUE**.  
  
 Флаги может иметь одно или несколько из следующих значений:  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData  
 Содержит указатель на структуру, созданные пользователем.  
  
### <a name="remarks"></a>Примечания  
 Это можно использовать для хранения данных печати, не следует хранить в классе представления. **M_lpUserData** элемента — это открытая переменная типа **LPVOID**.  
  
##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage  
 Содержит номер текущей страницы.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает `CView::OnPrepareDC` и `CView::OnPrint` один раз для каждой страницы документа, указав другое значение для этого элемента каждый раз; его значения в диапазоне от значения, возвращенного `GetFromPage` в возвращенном `GetToPage`. Этот элемент можно использовать в вашей переопределения `CView::OnPrepareDC` и `CView::OnPrint` печать указанной страницы документа.  
  
 При вызове режим предварительного просмотра framework считывает значение этого элемента, чтобы определить, какие страницы документа должен просматриваться изначально. Можно задать значение этого элемента в переопределении `CView::OnPreparePrinting` для поддержания пользователя текущую позицию в документе при переходе в режим предварительного просмотра. `m_nCurPage` Элемента — это открытая переменная типа **UINT**.  
  
##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber  
 Указывает номер задания, назначенный операционной системой для текущего задания печати.  
  
### <a name="remarks"></a>Примечания  
 Это значение может быть **SP_ERROR** Если задание еще не выдает (то есть, если `CPrintInfo` объект вновь создан и еще не использовался для печати), или произошла ошибка при запуске задания.  
  
##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages  
 Содержит количество страниц, отображаемых в режиме предварительного просмотра; он может быть 1 или 2.  
  
### <a name="remarks"></a>Примечания  
 **M_nNumPreviewPages** элемента — это открытая переменная типа **UINT**.  
  
##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage  
 Содержит номер страницы перед первой страницы определенного DocObject в объединенный DocObject задания печати.  
  
##  <a name="m_ppd"></a>  CPrintInfo::m_pPD  
 Содержит указатель на `CPrintDialog` объект, используемый для отображения диалоговое окно печати задания печати.  
  
### <a name="remarks"></a>Примечания  
 `m_pPD` Элемента — это открытая переменная, объявленная как указатель на `CPrintDialog`.  
  
##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw  
 Указывает область рисования можно использовать страницы в логических координатах.  
  
### <a name="remarks"></a>Примечания  
 Вы можете ссылаться на это в переопределении `CView::OnPrint`. Этот элемент можно использовать для отслеживания какой области остается доступной, после печати заголовки, нижние колонтитулы и т. д. **M_rectDraw** элемента — это открытая переменная типа `CRect`.  
  
##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc  
 Содержит строку формата, используемый для отображения номеров страниц во время предварительного просмотра; Эта строка состоит из двух подстрок, один для отображения одной страницы и один для отображения страницы double, каждый оканчивается символом «\n».  
  
### <a name="remarks"></a>Примечания  
 Платформа использует «U-%u\n % %u\nPages страницы» как значение по умолчанию. Если требуется другой формат для номеров страниц, задайте строку формата в переопределении `CView::OnPreparePrinting`. **M_strPageDesc** элемента — это открытая переменная типа `CString`.  
  
##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage  
 Вызывайте эту функцию, чтобы указать номер последней страницы документа.  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>Параметры  
 *nMaxPage*  
 Номер последней страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член. Если известны длине документа перед печатью, эта функция вызывается из переопределенный `CView::OnPreparePrinting`. Если длина документа зависит от параметра, указанное пользователем в диалоговом окне «Печать», эта функция вызывается из переопределенный `CView::OnBeginPrinting`. Если длина документа не известен до печати, используйте `m_bContinuePrinting` член для управления циклом печати.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="setminpage"></a>  CPrintInfo::SetMinPage  
 Вызывайте эту функцию, чтобы указать номер первой страницы документа.  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>Параметры  
 *nMinPage*  
 Номер первой страницы документа.  
  
### <a name="remarks"></a>Примечания  
 Номера страниц обычно начинаются с 1. Это значение хранится в `CPrintDialog` объект, упоминаемый в `m_pPD` член.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)   
 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)   
 [CView::OnPrint](../../mfc/reference/cview-class.md#onprint)



