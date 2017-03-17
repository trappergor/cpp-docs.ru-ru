---
title: "Класс CButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
dev_langs:
- C++
helpviewer_keywords:
- CButton class
- checkbox buttons
- pushbuttons
- button control [MFC]
- check boxes, button controls
- button objects (CButton)
- radio buttons, CButton class
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 751d4aee2c734acd455734ca694eb88bb149fc09
ms.lasthandoff: 02/24/2017

---
# <a name="cbutton-class"></a>Класс CButton
Предоставляет функциональные возможности кнопочных элементов управления Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CButton : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CButton::CButton](#cbutton)|Создает объект `CButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CButton::Create](#create)|Создает элемент управления button в Windows и присоединяет его к `CButton` объекта.|  
|[CButton::DrawItem](#drawitem)|Переопределение для рисования, рисуемого владельцем `CButton` объекта.|  
|[CButton::GetBitmap](#getbitmap)|Получает дескриптор точечного рисунка, заданные ранее с [SetBitmap](#setbitmap).|  
|[CButton::GetButtonStyle](#getbuttonstyle)|Получает сведения о стиле элемента управления кнопки.|  
|[CButton::GetCheck](#getcheck)|Получает состояние проверки элемента управления button.|  
|[CButton::GetCursor](#getcursor)|Получает дескриптор изображения курсора, заданные ранее с [SetCursor](#setcursor).|  
|[CButton::GetIcon](#geticon)|Получает дескриптор значка при помощи [SetIcon](#seticon).|  
|[CButton::GetIdealSize](#getidealsize)|Извлекает идеальный размер элемента управления button.|  
|[CButton::GetImageList](#getimagelist)|Получает список изображений элемента управления button.|  
|[CButton::GetNote](#getnote)|Получает компонент Примечание текущий элемент управления command link.|  
|[CButton::GetNoteLength](#getnotelength)|Получает длину текста для текущий элемент управления command link.|  
|[CButton::GetSplitGlyph](#getsplitglyph)|Извлекает глифов, связанных с текущей управления SplitButton.|  
|[CButton::GetSplitImageList](#getsplitimagelist)|Получает список изображений для текущего управления SplitButton.|  
|[CButton::GetSplitInfo](#getsplitinfo)|Возвращает информацию, которая определяет текущий элемент управления SplitButton.|  
|[CButton::GetSplitSize](#getsplitsize)|Возвращает прямоугольник, ограничивающий компонента раскрывающегося списка для текущего управления SplitButton.|  
|[CButton::GetSplitStyle](#getsplitstyle)|Получает стили кнопок разбиения, определяющие текущего управления SplitButton.|  
|[CButton::GetState](#getstate)|Получает состояние флажка, состояние выделения и состояние фокуса с элемента управления button.|  
|[CButton::GetTextMargin](#gettextmargin)|Получает текстовое поле элемента управления button.|  
|[CButton::SetBitmap](#setbitmap)|Задает растровое изображение для отображения на кнопке.|  
|[CButton::SetButtonStyle](#setbuttonstyle)|Изменение стиля кнопки.|  
|[CButton::SetCheck](#setcheck)|Задает состояние проверки элемента управления button.|  
|[CButton::SetCursor](#setcursor)|Указывает образ курсор, отображаемый на кнопке.|  
|[CButton::SetDropDownState](#setdropdownstate)|Задает состояние текущего управления SplitButton раскрывающегося списка.|  
|[CButton::SetIcon](#seticon)|Задает значок, отображаемый на кнопке.|  
|[CButton::SetImageList](#setimagelist)|Задает список изображений элемента управления button.|  
|[CButton::SetNote](#setnote)|Задает заметку на текущий элемент управления command link.|  
|[CButton::SetSplitGlyph](#setsplitglyph)|Связывает указанный глиф с текущего управления SplitButton.|  
|[CButton::SetSplitImageList](#setsplitimagelist)|Связывает список изображений с текущего управления SplitButton.|  
|[CButton::SetSplitInfo](#setsplitinfo)|Задает информацию, которая определяет текущий элемент управления SplitButton.|  
|[CButton::SetSplitSize](#setsplitsize)|Задает ограничивающий прямоугольник компонента раскрывающегося списка для текущего управления SplitButton.|  
|[CButton::SetSplitStyle](#setsplitstyle)|Задает стиль текущего управления SplitButton.|  
|[CButton::SetState](#setstate)|Задает состояние выделения элемента управления button.|  
|[CButton::SetTextMargin](#settextmargin)|Задает поле текста элемента управления button.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления button является небольшой прямоугольный дочернего окна, можно выбрать включение и отключение. Кнопки можно использовать отдельно или в группах и могут иметь пометки отображаются без текста. Кнопка обычно изменяется внешний вид, когда пользователь щелкает его.  
  
 Флажок, переключатель и pushbutton, являются обычные кнопки. Объект `CButton` объект может быть любой из них, согласно [кнопку стиля](../../mfc/reference/button-styles.md) указан при его инициализации, [создать](#create) функции-члена.  
  
 Кроме того [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) класс, производный от `CButton` поддерживает создание кнопок, меток, относящихся к растровым изображениям вместо текста. Объект `CBitmapButton` может иметь отдельное точечное изображение для кнопки элемента, вниз, фокус и отключить состояний.  
  
 Элемент управления button можно создать из шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CButton` для создания `CButton` объекта, затем вызовите **создать** функции-члена для создания окна управления «кнопка» и присоединить его к `CButton` объекта.  
  
 Построение может быть задачей в класс, производный от `CButton`. Создание конструктора для производного класса и вызове **создать** из внутри конструктора.  
  
 Если требуется обрабатывать сообщения уведомления Windows, отправленные элемент управления button с родительским (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавление карты сообщение входа и обработчик сообщений функции-члена родительский класс для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_**Notification **(**`id`, `memberFxn`**)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления отправки уведомлений и `memberFxn` имя родительской функции члена, написанный для обработки уведомления.  
  
 Прототип функции родительского выглядит следующим образом:  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 Схемы сообщений записей выглядят следующим образом:  
  
|Запись сопоставления|Отправляется, когда родительский...|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|Пользователь нажимает кнопку.|  
|**ON_BN_DOUBLECLICKED**|Пользователь дважды щелкает кнопку.|  
  
 При создании `CButton` из ресурса диалогового окна, `CButton` объект автоматически уничтожается, когда пользователь закрывает окно.  
  
 При создании `CButton` объекта в окне, необходимо уничтожить его. При создании `CButton` объектов в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь закрывает Windows управления «кнопка». При создании `CButton` объект в стеке или он внедрен в диалоговом окне родительский объект, он будет удален автоматически.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cbutton"></a>CButton::CButton  
 Создает объект `CButton`.  
  
```  
CButton();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#1;](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="create"></a>CButton::Create  
 Создает элемент управления button в Windows и присоединяет его к `CButton` объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszCaption`  
 Задает текст элемента управления button.  
  
 `dwStyle`  
 Задает стиль элемента управления button. Примените любое сочетание [кнопку Стили](../../mfc/reference/button-styles.md) к кнопке.  
  
 `rect`  
 Задает размер и положение элемента управления button. Это может быть либо `CRect` объекта или `RECT` структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления button, обычно `CDialog`. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CButton` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления button в Windows и присоединяет его к `CButton` объекта.  
  
 Если **WS_VISIBLE** задан стиль, Windows отправляет элемент управления button, все сообщения, необходимые для активации и Показывать кнопку.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) к элементу управления кнопки:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_GROUP** для группирования элементов управления  
  
- **WS_TABSTOP** для включения кнопки в порядке табуляции  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#2;](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="drawitem"></a>CButton::DrawItem  
 Вызывается инфраструктурой при изменении внешнего вида кнопки пользователем.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Длинный указатель [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуры. Структура содержит сведения о рисуемого элемента и типа требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 Определяемые владельцем кнопка имеет **BS_OWNERDRAW** набор стилей. Переопределить эту функцию-член для реализации отрисовки рисуемого владельцем `CButton` объекта. Приложение должно восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct` до элемента завершении функции.  
  
 См. также [BS_](../../mfc/reference/button-styles.md) стиля значения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#3;](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="getbitmap"></a>CButton::GetBitmap  
 Вызовите эту функцию-член для получения дескриптора точечного рисунка, заданные ранее с [SetBitmap](#setbitmap), связанный с кнопкой.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор точечного рисунка. **NULL** Если ранее не точечного рисунка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#4;](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="getbuttonstyle"></a>CButton::GetButtonStyle  
 Получает сведения о стиле элемента управления кнопки.  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает стили кнопок для этого `CButton` объекта. Эта функция возвращает только [BS_](../../mfc/reference/button-styles.md) значения стиля, не любой другой стиль окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#5;](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="getcheck"></a>CButton::GetCheck  
 Получает состояние флажка, переключателя или флажка.  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение из элемента управления кнопки создан с **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, или **BS_3STATE** стиль является одним из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|**BST_UNCHECKED**|Состояние кнопки не установлен.|  
|**BST_CHECKED**|Проверка состояния кнопки.|  
|**BST_INDETERMINATE**|Неопределенное состояние кнопки (применяется только в том случае, если кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиль).|  
  
 Если кнопка имеет другие стили, возвращаемое значение является **BST_UNCHECKED**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton №&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="getcursor"></a>CButton::GetCursor  
 Вызовите эту функцию-член получить дескриптор курсора, при помощи [SetCursor](#setcursor), связанный с кнопкой.  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для изображения курсора. **Значение NULL,** ранее указываемое без курсора.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#7;](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="geticon"></a>CButton::GetIcon  
 Вызовите эту функцию-член получить дескриптор значка, при помощи [SetIcon](#seticon), связанный с кнопкой.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для значка. **NULL** Если значок не задан ранее.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton №&8;](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="getidealsize"></a>CButton::GetIdealSize  
 Возвращает наилучший размер элемента управления button.  
  
```  
BOOL GetIdealSize(SIZE* psize);
```  
  
### <a name="parameters"></a>Параметры  
 *psize*  
 Указатель на текущий размер кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_GETIDEALSIZE** сообщений, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) раздел [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getimagelist"></a>CButton::GetImageList  
 Этот метод используется для получения списка изображений из элемента управления кнопки.  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Параметры  
 `pbuttonImagelist`  
 Указатель на список изображений `CButton` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_GETIMAGELIST** сообщений, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) раздел [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnote"></a>CButton::GetNote  
 Извлекает текст заметки, связанный с текущей элемент управления command link.  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpszNote`|Указатель на буфер, вызывающий объект отвечает за выделение и освобождение. Если возвращаемое значение является `true`, буфер содержит текст заметки, связанные с текущей элемент управления command link; в противном случае, буфера не изменяется.|  
|[in, out] `cchNote`|Указатель на переменную целого числа без знака.<br /><br /> При вызове этого метода переменная содержит размер буфера, указанного в `lpszNote` параметре.<br /><br /> Если этот метод возвращает, если возвращается значение `true` переменная содержит размер заметки, связанные с текущей элемент управления command link. Если возвращаемое значение является `false`, переменная содержит размер буфера, необходимый для размещения заметки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой перегрузке [CString](../../atl-mfc-shared/using-cstring.md) объекта, содержащего текст заметки, связанные с текущей элемент управления command link.  
  
 -или-  
  
 Во второй перегрузке `true` Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_COMMANDLINK` или `BS_DEFCOMMANDLINK`.  
  
 Этот метод отправляет [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnotelength"></a>CButton::GetNoteLength  
 Получает длину текста для текущий элемент управления command link.  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина текста заметки, в 16-разрядных символов Юникода для текущий элемент управления command link.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_COMMANDLINK` или `BS_DEFCOMMANDLINK`.  
  
 Этот метод отправляет [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getsplitglyph"></a>CButton::GetSplitGlyph  
 Извлекает глифов, связанных с текущей управления SplitButton.  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Глиф символ, связанный с текущей управления SplitButton.  
  
### <a name="remarks"></a>Примечания  
 Глиф является физическое представление символа в определенном шрифте. Например, элемент управления split button может быть оформлен глиф флажок символа Юникода (U +&2713;).  
  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_GLYPH` флаг, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. При возврате из функции сообщения, этот метод получает глиф из `himlGlyph` член структуры.  
  
##  <a name="getsplitimagelist"></a>CButton::GetSplitImageList  
 Извлекает [списка изображений](../../mfc/reference/cimagelist-class.md) для текущего управления SplitButton.  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_IMAGE` флаг, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. При возврате из функции сообщения, этот метод извлекает список изображений из `himlGlyph` член структуры.  
  
##  <a name="getsplitinfo"></a>CButton::GetSplitInfo  
 Получает параметры, которые определяют, каким образом Windows выводит текущий элемент управления SplitButton.  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pInfo`|Указатель на [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры, который получает сведения о текущем управления SplitButton. Вызывающий объект отвечает за выделение структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод отправляет [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getsplitsize"></a>CButton::GetSplitSize  
 Возвращает прямоугольник, ограничивающий компонента раскрывающегося списка для текущего управления SplitButton.  
  
```  
BOOL GetSplitSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pSize`|Указатель на [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуру, которая получает описание прямоугольника.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 При развертывании управления SplitButton, она может содержать компонент раскрывающегося списка, как список управления или элемент управления страничного навигатора. Этот метод получает ограничивающего прямоугольника, который содержит компонент раскрывающегося списка.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_SIZE` флаг, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. При возврате из функции сообщения, этот метод возвращает прямоугольник, ограничивающий из `size` член структуры.  
  
##  <a name="getsplitstyle"></a>CButton::GetSplitStyle  
 Получает стили кнопок разбиения, определяющие текущего управления SplitButton.  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание стили кнопок разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Стили кнопок разбиения укажите выравнивание, пропорции и графически, с помощью которого Windows выводит значок кнопки разбиения.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_STYLE` флаг, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. При возврате из функции сообщения, этот метод получает стили кнопок разбиения из `uSplitStyle` член структуры.  
  
##  <a name="getstate"></a>CButton::GetState  
 Возвращает состояние элемента управления button.  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Битовое поле, которое содержит комбинацию значений, которые указывают текущее состояние элемента управления button. В следующей таблице перечислены возможные значения.  
  
|Состояния кнопок|Значение|Описание|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|Начальное состояние.|  
|`BST_CHECKED`|0x0001|Установлен элемент управления button.|  
|`BST_INDETERMINATE`|0x0002|Состояние — неопределенное (возможна, только если элемент управления button имеет три состояния).|  
|`BST_PUSHED`|0x0004|Нажата кнопка.|  
|`BST_FOCUS`|0x0008|Кнопка управления имеет фокус.|  
  
### <a name="remarks"></a>Примечания  
 Элемент управления button с `BS_3STATE` или `BS_AUTO3STATE` стиль кнопки создает флажок для третьего состояния с именем неопределенное состояние. Неопределенное состояние указывает, что флажок не установлен и не снят флажок.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton №&9;](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="gettextmargin"></a>CButton::GetTextMargin  
 Вызовите этот метод, чтобы получить размер текстового поля `CButton` объекта.  
  
```  
BOOL GetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Параметры  
 `pmargin`  
 Указатель на размер текстового поля `CButton` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовое поле.  
  
### <a name="remarks"></a>Примечания  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_GETTEXTMARGIN** сообщений, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) раздел [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbitmap"></a>CButton::SetBitmap  
 Вызовите эту функцию-член для связывания нового растрового изображения с помощью кнопки.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `hBitmap`  
 Дескриптор точечного рисунка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор точечного рисунка, ранее связанные с кнопкой.  
  
### <a name="remarks"></a>Примечания  
 Растровое изображение будет автоматически помещено на лицевой стороне кнопки, по центру по умолчанию. Если точечный рисунок слишком велик для кнопки, он будет обрезан с обеих сторон. Можно выбрать другие параметры выравнивания, включая следующие:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), который использует четыре растровые изображения на кнопке, `SetBitmap` использует только один растрового изображения на кнопке. При нажатии кнопки появляется точечный рисунок необходимо сдвинуть вниз и вправо.  
  
 Вы несете ответственность за освобождение точечного рисунка, когда закончите с ним.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#4;](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="setbuttonstyle"></a>CButton::SetButtonStyle  
 Изменение стиля кнопки.  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nStyle`  
 Указывает [кнопку стиля](../../mfc/reference/button-styles.md).  
  
 `bRedraw`  
 Указывает, является ли кнопки перерисовку. Ненулевое значение — перерисовывает кнопку. Значение 0 не будут перерисовываться кнопки. По умолчанию перерисовке кнопки.  
  
### <a name="remarks"></a>Примечания  
 Используйте `GetButtonStyle` функции-члена для получения стиль кнопки. Младшее слово стиля кнопки завершения — это стиль кнопками.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#5;](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="setcheck"></a>CButton::SetCheck  
 Устанавливает или сбрасывает состояние флажка, переключателя или флажка.  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 `nCheck`  
 Указывает состояние флажка. Этот параметр может иметь одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|**BST_UNCHECKED**|Значение состояния кнопки флажок снят.|  
|**BST_CHECKED**|Задайте состояние кнопки проверить.|  
|**BST_INDETERMINATE**|Значение неопределенное состояние кнопки. Это значение может использоваться только в том случае, если кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиль.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член не влияет на кнопки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton №&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="setcursor"></a>CButton::SetCursor  
 Вызовите эту функцию-член для связывания нового курсора с помощью кнопки.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Параметры  
 `hCursor`  
 Дескриптор курсора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсора, ранее связанные с кнопкой.  
  
### <a name="remarks"></a>Примечания  
 Курсор автоматически помещается на лицевой стороне кнопки, по центру по умолчанию. Если курсор находится слишком велик для кнопки, он будет обрезан с обеих сторон. Можно выбрать другие параметры выравнивания, включая следующие:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), который использует четыре растровые изображения на кнопке, `SetCursor` использует только один курсор на кнопке. При нажатии на кнопку курсор кажется сместить вниз и вправо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton&#7;](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="setdropdownstate"></a>CButton::SetDropDownState  
 Задает состояние текущего управления SplitButton раскрывающегося списка.  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `fDropDown`|`true`Чтобы задать `BST_DROPDOWNPUSHED` состоянии; в противном случае — `false`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления split button имеет стиль `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON` и состоит из кнопки и стрелку раскрывающегося списка справа. Дополнительные сведения см. в разделе [стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb775951). Как правило состояние раскрывающегося списка устанавливается при щелчке стрелки раскрывающегося списка. Используйте этот метод, чтобы программно задать состояние элемента управления раскрывающегося списка. Стрелку раскрывающегося списка отображается затененным для указания состояния.  
  
 Этот метод отправляет [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_splitButton`, который используется для программного доступа к управления SplitButton. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает состояние управления SplitButton для указания, что помещается стрелку раскрывающегося списка.  
  
 [!code-cpp[NVC_MFC_CButton_s1 №&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="setelevationrequired"></a>CButton::SetElevationRequired  
 Задает состояние текущего элемента управления кнопки на `elevation required`, который необходим для элемента управления для отображения значка повышенных привилегий.  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `fElevationRequired`|`true`Чтобы задать `elevation required` состоянии; в противном случае — `false`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если кнопки или команды элемента управления ссылки требуются повышенные разрешения для выполнения действия, значение элемента управления `elevation required` состояние. Впоследствии Windows отображает значок щита управления учетных записей (UAC) в элементе управления. Дополнительные сведения см. в разделе «Контроль учетных записей пользователей» в [MSDN](http://go.microsoft.com/fwlink/linkid=18507).  
  
 Этот метод отправляет [BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="seticon"></a>CButton::SetIcon  
 Вызовите эту функцию-член, чтобы привязать новый значок кнопки.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 `hIcon`  
 Дескриптор значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значка ранее с помощью кнопки.  
  
### <a name="remarks"></a>Примечания  
 Значок будет автоматически помещается на лицевой стороне кнопки, по центру по умолчанию. Если значок слишком велик для кнопки, он будет обрезан с обеих сторон. Можно выбрать другие параметры выравнивания, включая следующие:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), который использует четыре растровые изображения на кнопке, `SetIcon` использует только один значок на кнопке. При нажатии кнопки, значок отображается сместить вниз и вправо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton №&8;](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="setimagelist"></a>CButton::SetImageList  
 Вызовите этот метод, чтобы задать список изображений `CButton` объекта.  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Параметры  
 `pbuttonImagelist`  
 Указатель на новый список изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_SETIMAGELIST** сообщений, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) раздел [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setnote"></a>CButton::SetNote  
 Задает текст текущего элемента управления ссылки команды.  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `lpszNote`|Указатель на строку Юникода, заданный как текст заметки для элемент управления command link.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_COMMANDLINK` или `BS_DEFCOMMANDLINK`.  
  
 Этот метод отправляет [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_cmdLink`, который используется для программного доступа к элемент управления command link. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает текст заметки для элемент управления command link.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="setsplitglyph"></a>CButton::SetSplitGlyph  
 Связывает указанный глиф с текущего управления SplitButton.  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `chGlyph`|Символ, указывающий глиф для использования в качестве разбиения стрелку раскрывающегося списка.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с помощью элементов управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Глиф является физическое представление символа в определенном шрифте. `chGlyph`Параметр не используется в качестве глифа, но вместо этого используется для выбора глиф из набора глифов, определяемые системой. Глиф стрелку раскрывающегося списка по умолчанию определяется символ '6' и напоминает символ Юникода вниз ЧЕРНЫЙ ТРЕУГОЛЬНИК (U +&25;BC).  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_GLYPH` флаг и `himlGlyph` член с `chGlyph` параметр, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setsplitimagelist"></a>CButton::SetSplitImageList  
 Связывает [списка изображений](../../mfc/reference/cimagelist-class.md) с текущего управления SplitButton.  
  
```  
BOOL SetSplitImageList(CImageList* pSplitImageList);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pSplitImageList`|Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект для назначения текущего управления SplitButton.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_IMAGE` флаг и `himlGlyph` член с `pSplitImageList` параметр, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setsplitinfo"></a>CButton::SetSplitInfo  
 Указывает параметры, которые определяют, каким образом Windows выводит текущий элемент управления SplitButton.  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pInfo`|Указатель на [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура, определяющая текущего управления SplitButton.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод отправляет [BCM_SETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775981) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_splitButton`, который используется для программного доступа к управления SplitButton.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода изменяется на глиф, который используется для разбиения стрелку раскрывающегося списка. В примере подставляются направленной вверх глиф треугольник глифа треугольник направленной вниз по умолчанию. Глиф, который отображается зависит от символа, указанного в `himlGlyph` членом `BUTTON_SPLITINFO` структуры. Глиф направленной вниз треугольник указан символ "6"и глиф треугольник направленной вверх указан символ '&5;". Для сравнения см. метод удобства [CButton::SetSplitGlyph](#setsplitglyph).  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
##  <a name="setsplitsize"></a>CButton::SetSplitSize  
 Задает ограничивающий прямоугольник компонента раскрывающегося списка для текущего управления SplitButton.  
  
```  
BOOL SetSplitSize(LPSIZE pSize);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pSize`|Указатель на [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структура, описывающая ограничивающего прямоугольника.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 При развертывании управления SplitButton, она может содержать компонент раскрывающегося списка, как список управления или элемент управления страничного навигатора. Этот метод задает размер ограничивающего прямоугольника, который содержит компонент раскрывающегося списка.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_SIZE` флаг и `size` член с `pSize` параметр, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_splitButton`, который используется для программного доступа к управления SplitButton. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере удваивается объем разбиения стрелку раскрывающегося списка.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="setsplitstyle"></a>CButton::SetSplitStyle  
 Задает стиль текущего управления SplitButton.  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `uSplitStyle`|Побитовое сочетание стили кнопок разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод только с элементами управления, стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Стили кнопок разбиения укажите выравнивание, пропорции и графически, с помощью которого Windows выводит значок кнопки разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_STYLE` флаг и `uSplitStyle` член с `uSplitStyle` параметр, а затем отправляет, структуре [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_splitButton`, который используется для программного доступа к управления SplitButton.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает стиль разбиения стрелку раскрывающегося списка. `BCSS_ALIGNLEFT` Отображение стрелку слева от кнопки, а `BCSS_STRETCH` стиля сохраняет пропорции стрелку раскрывающегося списка, при изменении размера кнопки.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="setstate"></a>CButton::SetState  
 Определяет, будет выделен элемент управления button или нет.  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Параметры  
 *bHighlight*  
 Указывает, является ли кнопки выделены. Ненулевое значение выделяет кнопки. значение 0 удаляет все выделение.  
  
### <a name="remarks"></a>Примечания  
 Выделение влияет на внешней элемент управления button. Он не влияет на состояние флажка, переключателя или флажка.  
  
 Элемент управления button автоматически выделяется, когда пользователь нажимает и удерживает левую кнопку мыши. Выделение удаляется, когда пользователь отпускает кнопку мыши.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton №&9;](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="settextmargin"></a>CButton::SetTextMargin  
 Вызовите этот метод, чтобы задать размер текстового поля `CButton` объекта.  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Параметры  
 `pmargin`  
 Указатель на поле новый текст.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_SETTEXTMARGIN** сообщений, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) раздел [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)   
 [Класс CStatic](../../mfc/reference/cstatic-class.md)   
 [Класс CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)

