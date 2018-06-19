---
title: Класс CStatic | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d3b1a5dcfc8481727bffd8b80e0bb1b230d56ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375008"
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
|[CStatic::Create](#create)|Создает статический элемент управления Windows и прикрепляет его к `CStatic` объекта.|  
|[CStatic::DrawItem](#drawitem)|Переопределите, чтобы нарисовать определяемый владельцем статический элемент управления.|  
|[CStatic::GetBitmap](#getbitmap)|Извлекает дескриптор растрового изображения при помощи [SetBitmap](#setbitmap).|  
|[CStatic::GetCursor](#getcursor)|Возвращает дескриптор курсора изображения ранее задан с [SetCursor](#setcursor).|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Извлекает дескриптор расширенного метафайла, при помощи [SetEnhMetaFile](#setenhmetafile).|  
|[CStatic::GetIcon](#geticon)|Извлекает дескриптор значка при помощи [SetIcon](#seticon).|  
|[CStatic::SetBitmap](#setbitmap)|Задает растровое изображение для отображения в статический элемент управления.|  
|[CStatic::SetCursor](#setcursor)|Указывает образ курсор, отображаемый на статический элемент управления.|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Указывает расширенный метафайл для отображения в статический элемент управления.|  
|[CStatic::SetIcon](#seticon)|Задает значок, отображаемый на статический элемент управления.|  
  
## <a name="remarks"></a>Примечания  
 Статический элемент управления отображает текстовую строку, поле, прямоугольник, значок, курсор, растровое изображение или расширенный метафайл. Он может использоваться для метки, поле или разделения других элементов управления. Статический элемент управления обычно не принимает входные данные и предоставляет выходные данные; Тем не менее, его можно уведомить родительского объекта щелчки мышью создается с **SS_NOTIFY** стиля.  
  
 Создание статического элемента управления в два этапа. Во-первых, вызовите конструктор для создания `CStatic` объекта, а затем вызвать [создать](#create) функции-члена для создания статического элемента управления и присоединить его к `CStatic` объекта.  
  
 Если вы создаете `CStatic` объектов в диалоговом окне (с помощью ресурса диалогового окна) `CStatic` объект автоматически освобождается, когда пользователь закрывает диалоговое окно.  
  
 Если вы создаете `CStatic` объекта в окне, может потребоваться удалить его. Объект `CStatic` объект, созданный в стеке в окне автоматически уничтожается. При создании `CStatic` объекта в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда вы завершили работу с ним.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="create"></a>  CStatic::Create  
 Создает статический элемент управления Windows и прикрепляет его к `CStatic` объекта.  
  
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
 Указывает стиль окна статического элемента управления. Примените любое сочетание [стили статический элемент управления](../../mfc/reference/styles-used-by-mfc.md#static-styles) к элементу управления.  
  
 `rect`  
 Задает положение и размер статического элемента управления. Это может быть либо `RECT` структуры или `CRect` объекта.  
  
 `pParentWnd`  
 Указывает `CStatic` родительского окна, обычно `CDialog` объекта. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления статического элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создать `CStatic` объекта в два этапа. Во-первых, вызовите конструктор `CStatic`, а затем вызвать **создать**, который создает статический элемент управления Windows и прикрепляет его к `CStatic` объекта.  
  
 Применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) на статический элемент управления:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
 Если отобразить растровое изображение, курсора, значка или метафайла в статический элемент управления, необходимо применить один из следующих [статические стили](../../mfc/reference/styles-used-by-mfc.md#static-styles):  
  
- **SS_BITMAP** использовать этот стиль для растровых изображений.  
  
- **SS_ICON** использовать этот стиль для курсоров и значков.  
  
- **SS_ENHMETAFILE** использовать этот стиль для расширенные метафайлы.  
  
 Для курсоров, растровые изображения или значки можно также использовать следующий стиль:  
  
- **SS_CENTERIMAGE** используйте изображение в статический элемент управления по центру.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>  CStatic::CStatic  
 Создает объект `CStatic`.  
  
```  
CStatic();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>  CStatic::DrawItem  
 Вызывается платформой для отрисовки определяемый владельцем статический элемент управления.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуры. Структура содержит сведения о рисуемого элемента и типа требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для реализации отрисовки рисуемого владельцем **CStatic** объект (элемент управления имеет стиль **SS_OWNERDRAW**).  
  
##  <a name="getbitmap"></a>  CStatic::GetBitmap  
 Возвращает дескриптор растрового изображения, при помощи [SetBitmap](#setbitmap), связанные с `CStatic`.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего растрового изображения, или **NULL** Если нет растрового изображения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>  CStatic::GetCursor  
 Возвращает дескриптор курсора при помощи [SetCursor](#setcursor), связанные с `CStatic`.  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущий курсор или **NULL** Если никакой курсор не задана.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile  
 Возвращает дескриптор расширенного метафайла, при помощи [SetEnhMetafile](#setenhmetafile), связанные с `CStatic`.  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего расширенный метафайл или **NULL** Если нет Metafile — расширенный метафайл.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>  CStatic::GetIcon  
 Возвращает дескриптор значка, при помощи [SetIcon](#seticon), связанные с `CStatic`.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего значка или **NULL** Если значок не было задано.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>  CStatic::SetBitmap  
 Связывает новое растровое изображение с статического элемента управления.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `hBitmap`  
 Дескриптор растрового изображения для отображения статического элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор точечного рисунка, который был ранее связан с статического элемента управления или `NULL` Если был связан с статический элемент управления не растрового изображения.  
  
### <a name="remarks"></a>Примечания  
 Статический элемент управления автоматически отображаются растрового изображения. По умолчанию будет отображаться в левом верхнем углу, а статический элемент управления будет изменен для размер растрового изображения.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
-   SS_BITMAP всегда использовать этот стиль для растровых изображений.  
  
-   SS_CENTERIMAGE используйте изображение в статический элемент управления по центру. Если изображение больше, чем статического элемента управления, то он будет обрезан. Если это меньше, чем статического элемента управления, пустое пространство вокруг изображения заполненной цвет пикселя в верхнем левом углу растрового изображения.  
  
-   MFC предоставляет класс `CBitmap`, который можно использовать при наличии более с растровым изображением, чем просто вызвать Win32 функции `LoadBitmap`. `CBitmap`, содержащий одного типа объектов GDI, часто используется вместе с `CStatic`, который является `CWnd` класс, который используется для отображения графического объекта в качестве статического элемента управления.  
  
 `CImage` является классом ATL и MFC, который позволяет легко работать с независимыми растровые изображения устройства (DIB). Дополнительные сведения см. в разделе [CImage-класс](../../atl-mfc-shared/reference/cimage-class.md).  
  
-   Обычно используется для предоставления `CStatic::SetBitmap` объект GDI, возвращенный оператор HBITMAP `CBitmap` или `CImage` объекта. Код для этого, похожий на следующий.  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
В следующем примере создается два `CStatic` объектов в куче. Затем она загружает один с системой точечный рисунок с помощью `CBitmap::LoadOEMBitmap` , а другой из файла с помощью `CImage::Load`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>  CStatic::SetCursor  
 Связывает новый образ курсора с помощью статического элемента управления.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Параметры  
 `hCursor`  
 Дескриптор курсора в статический элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсора, связанный с статического элемента управления или **NULL** Если никакой курсор был связан с статического элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Курсор автоматически отображается в статический элемент управления. По умолчанию будет отображаться в левом верхнем углу, а статический элемент управления будет изменен для размера курсора.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
- **SS_ICON** всегда использовать этот стиль для курсоров и значков.  
  
- **SS_CENTERIMAGE** используйте, чтобы центрировать в статический элемент управления. Если изображение больше, чем статического элемента управления, то он будет обрезан. Если меньше статического элемента управления, пустое пространство вокруг изображения будут заполняться цветом фона статического элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile  
 Связывает новый образ Metafile — расширенный метафайл с статического элемента управления.  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>Параметры  
 `hMetaFile`  
 Дескриптор расширенного метафайла для отображения статического элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор расширенного метафайла, связанный с статического элемента управления или **NULL** Если нет Metafile — расширенный метафайл был связан с статического элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Расширенный метафайл автоматически отображается в статический элемент управления. Расширенный метафайл масштабируется до размеров статического элемента управления.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
- **SS_ENHMETAFILE** всегда использовать этот стиль для расширенные метафайлы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>  CStatic::SetIcon  
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
 Значок будет автоматически отображаться в статический элемент управления. По умолчанию будет отображаться в левом верхнем углу, а статический элемент управления будет изменен для размер значка.  
  
 Можно использовать различные окна и стили статического элемента управления, включая следующие:  
  
- **SS_ICON** всегда использовать этот стиль для курсоров и значков.  
  
- **SS_CENTERIMAGE** используйте, чтобы центрировать в статический элемент управления. Если изображение больше, чем статического элемента управления, то он будет обрезан. Если меньше статического элемента управления, пустое пространство вокруг изображения будут заполняться цветом фона статического элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)   
 [Класс CDialog](../../mfc/reference/cdialog-class.md)
