---
title: "Класс CStatic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
dev_langs:
- C++
helpviewer_keywords:
- enhanced metafiles
- cursors, displaying
- static controls
- controls [MFC], static
- icons, displaying
- CStatic class
- enhanced metafiles, displaying
- bitmaps, displaying
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0209fad1b84b782cdec7927cb5a04e9bb3083d64
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cstatic-class"></a>Класс CStatic
Предоставляет функции статического элемента управления Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CStatic : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStatic::CStatic](#cstatic)|Создает объект `CStatic`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStatic::Create](#create)|Статический элемент управления Windows создает и присоединяет его к `CStatic` объекта.|  
|[CStatic::DrawItem](#drawitem)|Переопределение для рисования пользовательского статический элемент управления.|  
|[CStatic::GetBitmap](#getbitmap)|Получает дескриптор точечного рисунка, заданные ранее с [SetBitmap](#setbitmap).|  
|[CStatic::GetCursor](#getcursor)|Получает дескриптор изображения курсора, заданные ранее с [SetCursor](#setcursor).|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Получает дескриптор расширенного метафайла, ранее было установлено с [SetEnhMetaFile](#setenhmetafile).|  
|[CStatic::GetIcon](#geticon)|Получает дескриптор значка при помощи [SetIcon](#seticon).|  
|[CStatic::SetBitmap](#setbitmap)|Задает растровое изображение для отображения в статический элемент управления.|  
|[CStatic::SetCursor](#setcursor)|Задает изображение для отображения в элементе управления статический курсор.|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Указывает расширенный метафайл, отображаемый в элементе управления статический.|  
|[CStatic::SetIcon](#seticon)|Задает значок, отображаемый в элементе управления статический.|  
  
## <a name="remarks"></a>Примечания  
 Статический элемент управления отображает текстовую строку, поле, прямоугольник, значка, курсора, растрового изображения или расширенный метафайл. Он может использоваться для метки, поле или разделения других элементов управления. Статический элемент управления обычно не принимает входные данные и предоставляет выходные данные; Тем не менее, его можно уведомлять родительского щелчков мыши создается с **SS_NOTIFY** стиль.  
  
 Создание статического элемента управления в два этапа. Во-первых, вызовите конструктор для создания `CStatic` , а затем вызвать [создать](#create) функции-члена для создания статического элемента управления и присоединить его к `CStatic` объекта.  
  
 При создании `CStatic` объекта в диалоговое окно (с помощью ресурса диалогового окна), `CStatic` объект автоматически уничтожается, когда пользователь закрывает окно.  
  
 При создании `CStatic` объекта в окне, необходимо уничтожить его. Объект `CStatic` объект, созданный в стеке в окне автоматически уничтожается. При создании `CStatic` объектов в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда вы завершили работу с ним.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="create"></a>CStatic::Create  
 Статический элемент управления Windows создает и присоединяет его к `CStatic` объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszText,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID = 0xffff);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Задает текст, записываемый в элементе управления. Если **NULL**, текст не будут видны.  
  
 `dwStyle`  
 Указывает стиль окна статического элемента управления. Примените любое сочетание [стили статический элемент управления](../../mfc/reference/static-styles.md) для элемента управления.  
  
 `rect`  
 Указывает положение и размер статического элемента управления. Это может быть либо `RECT` структуры или `CRect` объекта.  
  
 `pParentWnd`  
 Указывает `CStatic` родительского окна, обычно `CDialog` объекта. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор статический элемент управления элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создать `CStatic` объекта в два этапа. Во-первых, вызовите конструктор `CStatic`и затем вызвать **создать**, который создает статический элемент управления Windows и присоединяет его к `CStatic` объекта.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) на статический элемент управления:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
 Если вы собираетесь отображение статического элемента управления в точечный рисунок, курсор, значка или метафайла, необходимо применить один из следующих [статические стили](../../mfc/reference/static-styles.md):  
  
- **SS_BITMAP** использовать этот стиль для точечных рисунков.  
  
- **SS_ICON** использовать этот стиль для курсоров и значков.  
  
- **SS_ENHMETAFILE** использовать этот стиль для расширенные метафайлы.  
  
 Для курсоров точечные рисунки и значки можно также использовать следующий стиль:  
  
- **SS_CENTERIMAGE** используйте изображение в статический элемент управления по центру.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#1;](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>CStatic::CStatic  
 Создает объект `CStatic`.  
  
```  
CStatic();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#2;](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>CStatic::DrawItem  
 Вызывается платформой для рисования пользовательского статический элемент управления.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуры. Структура содержит сведения о рисуемого элемента и типа требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для реализации отрисовки рисуемого владельцем **CStatic** объекта (элемент управления имеет стиль **SS_OWNERDRAW**).  
  
##  <a name="getbitmap"></a>CStatic::GetBitmap  
 Возвращает дескриптор точечного рисунка, заданные ранее с [SetBitmap](#setbitmap), связанные с `CStatic`.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего растрового изображения, или **NULL** Если нет точечного рисунка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>CStatic::GetCursor  
 Возвращает дескриптор курсора при помощи [SetCursor](#setcursor), связанные с `CStatic`.  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего курсора или **NULL** Если никакой курсор не задана.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>CStatic::GetEnhMetaFile  
 Возвращает дескриптор расширенного метафайла, ранее было установлено с [SetEnhMetafile](#setenhmetafile), связанные с `CStatic`.  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего расширенный метафайл, или **NULL** Если не расширенный метафайл.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>CStatic::GetIcon  
 Получает дескриптор значка, при помощи [SetIcon](#seticon), связанные с `CStatic`.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего значка или **NULL** Если значок не задан.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic №&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>CStatic::SetBitmap  
 Связывает новый точечный рисунок с статического элемента управления.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `hBitmap`  
 Дескриптор точечного рисунка для отображения статического элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор точечного рисунка, который был ранее связан с статического элемента управления или `NULL` Если нет точечный рисунок был связан с статического элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Статический элемент управления автоматически отображаются точечного рисунка. По умолчанию будет отображаться в левом верхнем углу и статического элемента управления будет изменяться размер растрового изображения.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
-   SS_BITMAP всегда использовать этот стиль для точечных рисунков.  
  
-   SS_CENTERIMAGE используйте изображение в статический элемент управления по центру. Если изображение больше, чем статического элемента управления, он будет обрезан. Если это меньше, чем статический элемент управления, пустое пространство вокруг изображения будут заполняться цвет пикселя в верхнем левом углу точечного рисунка.  
  
-   MFC предоставляет класс `CBitmap`, который можно использовать при наличии более растрового изображения, чем просто вызвать Win32 функции `LoadBitmap`. `CBitmap`, содержащий одного типа объектов GDI, часто используется вместе с `CStatic`, который является `CWnd` класс, используемый для отображения графического объекта в виде статического элемента управления.  
  
 `CImage`является классом ATL и MFC, который позволяет легко работать с независимым растровые изображения устройства (DIB). Дополнительные сведения см. в разделе [класса CImage](../../atl-mfc-shared/reference/cimage-class.md).  
  
-   Обычно используется для предоставления `CStatic::SetBitmap` объект GDI, возвращаемый оператор HBITMAP `CBitmap` или `CImage` объекта. Код для этого, похожий на следующую строку.  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
В следующем примере создаются два `CStatic` объектов в куче. Затем он загружает один с системой точечный рисунок с помощью `CBitmap::LoadOEMBitmap` , а другой из файла с помощью `CImage::Load`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>CStatic::SetCursor  
 Связывает новое изображение курсора с помощью статического элемента управления.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Параметры  
 `hCursor`  
 Дескриптор курсора в статический элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсора, связанный с статического элемента управления или **NULL** Если курсор не был связан с статического элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Курсор будет автоматически отображаться в статический элемент управления. По умолчанию будет отображаться в левом верхнем углу и статического элемента управления будет изменен для размера курсора.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
- **SS_ICON** всегда использовать этот стиль для курсоров и значков.  
  
- **SS_CENTERIMAGE** использование статического элемента управления по центру. Если изображение больше, чем статического элемента управления, он будет обрезан. Если это меньше, чем статический элемент управления, пустое пространство вокруг изображения будет заполняться цвет фона статического элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>CStatic::SetEnhMetaFile  
 Связывает новый расширенный метафайл образ с статического элемента управления.  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>Параметры  
 `hMetaFile`  
 Дескриптор расширенного метафайла, отображаемый в элементе управления статический.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор расширенного метафайла, ранее связанные с статического элемента управления или **NULL** Если не расширенный метафайл был связан с статического элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Статический элемент управления автоматически отображаются расширенный метафайл. Расширенный метафайл масштабируется до размеров статического элемента управления.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
- **SS_ENHMETAFILE** всегда использовать этот стиль для расширенные метафайлы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic&#5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>CStatic::SetIcon  
 Связывает новое изображение значка с статического элемента управления.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 `hIcon`  
 Дескриптор значка для отображения статического элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значка ранее статического элемента управления или **NULL** Если значок не был связан с статического элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Значок будет автоматически отображаться в статический элемент управления. По умолчанию будет отображаться в левом верхнем углу и статический элемент управления будет изменяться размер значка.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
- **SS_ICON** всегда использовать этот стиль для курсоров и значков.  
  
- **SS_CENTERIMAGE** использование статического элемента управления по центру. Если изображение больше, чем статического элемента управления, он будет обрезан. Если это меньше, чем статический элемент управления, пустое пространство вокруг изображения будет заполняться цвет фона статического элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic №&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)

