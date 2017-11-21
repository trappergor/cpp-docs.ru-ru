---
title: "Класс CButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5eb955843d2390864a7fbc2c45025dca39ce498b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[CButton::Create](#create)|Создает элемент управления button в Windows и прикрепляет его к `CButton` объекта.|  
|[CButton::DrawItem](#drawitem)|Переопределение, чтобы нарисовать рисуемого владельцем `CButton` объекта.|  
|[CButton::GetBitmap](#getbitmap)|Извлекает дескриптор растрового изображения при помощи [SetBitmap](#setbitmap).|  
|[CButton::GetButtonStyle](#getbuttonstyle)|Извлекает сведения о стиле элемента управления button.|  
|[CButton::GetCheck](#getcheck)|Получает состояние проверки элемента управления button.|  
|[CButton::GetCursor](#getcursor)|Возвращает дескриптор курсора изображения ранее задан с [SetCursor](#setcursor).|  
|[CButton::GetIcon](#geticon)|Извлекает дескриптор значка при помощи [SetIcon](#seticon).|  
|[CButton::GetIdealSize](#getidealsize)|Извлекает идеальный размер элемента управления button.|  
|[CButton::GetImageList](#getimagelist)|Извлекает список изображений элемента управления button.|  
|[CButton::GetNote](#getnote)|Возвращает компонент Примечание текущего элемента управления ссылки команды.|  
|[CButton::GetNoteLength](#getnotelength)|Получает длину текста для текущей команды управления ссылками.|  
|[CButton::GetSplitGlyph](#getsplitglyph)|Извлекает глифов, связанных с текущей управления SplitButton.|  
|[CButton::GetSplitImageList](#getsplitimagelist)|Извлекает список изображений для текущего управления SplitButton.|  
|[CButton::GetSplitInfo](#getsplitinfo)|Получает сведения, определяющие текущего управления SplitButton.|  
|[CButton::GetSplitSize](#getsplitsize)|Возвращает прямоугольник, ограничивающий компонента раскрывающегося списка для текущего управления SplitButton.|  
|[CButton::GetSplitStyle](#getsplitstyle)|Извлекает стили кнопок разбиение, определяющие текущего управления SplitButton.|  
|[CButton::GetState](#getstate)|Извлекает состояние флажка, состояние выделения и состояние фокуса с элемента управления button.|  
|[CButton::GetTextMargin](#gettextmargin)|Извлекает поле текст для элемента управления button.|  
|[CButton::SetBitmap](#setbitmap)|Задает точечный рисунок, отображаемый на кнопке.|  
|[CButton::SetButtonStyle](#setbuttonstyle)|Изменяет стиль кнопки.|  
|[CButton::SetCheck](#setcheck)|Задает состояние проверки элемента управления button.|  
|[CButton::SetCursor](#setcursor)|Указывает образ курсор, отображаемый на кнопке.|  
|[CButton::SetDropDownState](#setdropdownstate)|Задает состояние текущего управления SplitButton раскрывающегося списка.|  
|[CButton::SetIcon](#seticon)|Задает значок, отображаемый на кнопке.|  
|[CButton::SetImageList](#setimagelist)|Задает список изображений элемента управления button.|  
|[CButton::SetNote](#setnote)|Задает примечание текущей команды управления ссылками.|  
|[CButton::SetSplitGlyph](#setsplitglyph)|Связывает указанный глифа с текущего управления SplitButton.|  
|[CButton::SetSplitImageList](#setsplitimagelist)|Связывает список изображений с текущего управления SplitButton.|  
|[CButton::SetSplitInfo](#setsplitinfo)|Задает сведения, определяющие текущего управления SplitButton.|  
|[CButton::SetSplitSize](#setsplitsize)|Задает ограничивающий прямоугольник компонента раскрывающегося списка для текущего управления SplitButton.|  
|[CButton::SetSplitStyle](#setsplitstyle)|Задает стиль текущего управления SplitButton.|  
|[CButton::SetState](#setstate)|Задает состояние выделения элемента управления button.|  
|[CButton::SetTextMargin](#settextmargin)|Задает поле текст элемента управления button.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления button является небольшой, прямоугольная дочернее окно, можно выбрать включение и отключение. Кнопки можно использовать отдельно или в группах и либо может быть меткой или отображаются без текста. Кнопка обычно изменяется внешний вид, когда пользователь нажимает кнопку.  
  
 Обычные кнопки являются флажок, переключателя и кнопки. Объект `CButton` объект может быть любой из них, согласно [кнопку стиль](../../mfc/reference/styles-used-by-mfc.md#button-styles) определено на его инициализация путем [создать](#create) функции-члена.  
  
 Кроме того [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) класс, производный от `CButton` поддерживает создание элементов управления с меткой с растровыми изображениями, а не текст. Объект `CBitmapButton` может иметь отдельные растровые изображения для кнопки элемента, вниз, с фокусом ввода и отключении.  
  
 Элемент управления button можно создать на основе шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CButton` для создания `CButton` объекта; затем вызвать **создать** функция-член для создания окна управления «кнопка» и присоединить его к `CButton` объекта.  
  
 Построение может быть задачей в классе, производном от `CButton`. Создание конструктора для производного класса и вызове **создать** из внутри конструктора.  
  
 Если вы хотите обработки сообщений Windows уведомление посылается кнопкой элемента управления своему родителю (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавить схему сообщений входа и обработчик сообщений функции-члена родительского класса для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_**уведомления **(**`id`, `memberFxn` **)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления, отправляющего уведомление и `memberFxn` имя функции-члена родительского вы написали для обработки уведомления.  
  
 Прототип функции родительского элемента выглядит следующим образом:  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 Схемы сообщений записей выглядят следующим образом:  
  
|Элемент карты|Отправлено в качестве родительского, когда...|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|Пользователь нажимает кнопку.|  
|**ON_BN_DOUBLECLICKED**|Пользователь дважды щелкает кнопкой.|  
  
 Если вы создаете `CButton` из ресурса диалогового окна, `CButton` объект автоматически освобождается, когда пользователь закрывает диалоговое окно.  
  
 Если вы создаете `CButton` объекта в окне, может потребоваться удалить его. При создании `CButton` объекта в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь закрывает окно управления «кнопка». Если вы создаете `CButton` объект в стеке или он внедрен в родительский объект диалогового окна, удаляется автоматически.  
  
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
 [!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="create"></a>CButton::Create  
 Создает элемент управления button в Windows и прикрепляет его к `CButton` объекта.  
  
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
 Задает стиль элемента управления button. Примените любое сочетание [кнопку Стили](../../mfc/reference/styles-used-by-mfc.md#button-styles) к кнопке.  
  
 `rect`  
 Задает размер и положение элемента управления button. Это может быть либо `CRect` объекта или `RECT` структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления button, обычно `CDialog`. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CButton` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления button в Windows и прикрепляет его к `CButton` объекта.  
  
 Если **WS_VISIBLE** задан стиль, Windows отправляет элемент управления button все сообщения, необходимые для активации и отображения кнопки.  
  
 Применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления кнопки:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_GROUP** для группировки элементов управления  
  
- **WS_TABSTOP** для включения кнопки в порядок перехода по табуляции  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="drawitem"></a>CButton::DrawItem  
 Вызывается платформой при изменении внешнего вида кнопки владельцем.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Длинный указатель [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуры. Структура содержит сведения о рисуемого элемента и типа требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 Определяемые владельцем кнопка имеет **BS_OWNERDRAW** стиля набора. Переопределить эту функцию-член для реализации отрисовки рисуемого владельцем `CButton` объекта. Приложения следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct` до элемента, функция завершается.  
  
 См. также [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) значений стиля.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="getbitmap"></a>CButton::GetBitmap  
 Вызовите эту функцию-член получить дескриптор растрового изображения, при помощи [SetBitmap](#setbitmap), связанный с кнопкой.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор к растровому изображению. **Значение NULL** Если ранее не растрового изображения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="getbuttonstyle"></a>CButton::GetButtonStyle  
 Извлекает сведения о стиле элемента управления button.  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает стили кнопок для этого `CButton` объекта. Эта функция возвращает только [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) значения стиля, не любой другой стиль окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="getcheck"></a>CButton::GetCheck  
 Получает состояние флажка "переключатель" или "флажок".  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение из элемента управления button создан с **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, или **BS_3STATE** стиль является одним из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|**BST_UNCHECKED**|Состояние кнопки не установлен.|  
|**BST_CHECKED**|Проверяется состояние кнопки.|  
|**BST_INDETERMINATE**|Неопределенное состояние кнопки (применяется только в том случае, если эта кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиль).|  
  
 Если эта кнопка имеет любой другой стиль, возвращаемое значение равно **BST_UNCHECKED**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="getcursor"></a>CButton::GetCursor  
 Вызовите эту функцию-член получить дескриптор курсора, при помощи [SetCursor](#setcursor), связанный с кнопкой.  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор изображения курсора. **Значение NULL** Если ранее указано без курсора.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="geticon"></a>CButton::GetIcon  
 Вызовите эту функцию-член получить дескриптор значка, при помощи [SetIcon](#seticon), связанный с кнопкой.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для значка. **Значение NULL** Если значок не задан ранее.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
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
 Эта функция-член эмулирует работу **BCM_GETIDEALSIZE** сообщения, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) части пакета Windows SDK.  
  
##  <a name="getimagelist"></a>CButton::GetImageList  
 Этот метод используется для получения списка изображений из элемента управления button.  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Параметры  
 `pbuttonImagelist`  
 Указатель на список изображений `CButton` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_GETIMAGELIST** сообщения, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) части пакета Windows SDK.  
  
##  <a name="getnote"></a>CButton::GetNote  
 Извлекает текст заметки, связанный с текущей команды управления ссылками.  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpszNote`|Указатель на буфер, вызывающий объект отвечает за выделение и освобождение. Если возвращается значение `true`, буфер содержит текст заметки, связанные с текущего элемента управления ссылки команды; в противном случае, буфер не изменяется.|  
|[in, out] `cchNote`|Указатель на переменную целого числа без знака.<br /><br /> При вызове этого метода переменная содержит размер буфера, определяемое `lpszNote` параметра.<br /><br /> Этот метод возвращает, если возвращается значение `true` переменная содержит размер заметки, связанные с текущей команды управления ссылками. Если возвращается значение `false`, переменная содержит размер буфера, необходимый для размещения заметки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой перегрузке [CString](../../atl-mfc-shared/using-cstring.md) объекта, содержащего текст заметки, связанные с текущей команды управления ссылками.  
  
 -или-  
  
 Во второй перегрузке `true` Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_COMMANDLINK` или `BS_DEFCOMMANDLINK`.  
  
 Этот метод отправляет [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965) сообщение, которое описано в Windows SDK.  
  
##  <a name="getnotelength"></a>CButton::GetNoteLength  
 Получает длину текста для текущей команды управления ссылками.  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина текста заметки, в 16-битовых символов Юникода, для текущей команды управления ссылками.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_COMMANDLINK` или `BS_DEFCOMMANDLINK`.  
  
 Этот метод отправляет [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967) сообщение, которое описано в Windows SDK.  
  
##  <a name="getsplitglyph"></a>CButton::GetSplitGlyph  
 Извлекает глифов, связанных с текущей управления SplitButton.  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Глиф символ, связанный с текущей управления SplitButton.  
  
### <a name="remarks"></a>Примечания  
 Глиф является физическое представление символа в определенном шрифте. Например, элемент управления SplitButton может быть снабжен атрибутом глиф флажок символа Юникода (U + 2713).  
  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_GLYPH` флаг, а затем отправляет, структуры в [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) описанное в Windows SDK. При возврате функция сообщения, этот метод получает глиф из `himlGlyph` член структуры.  
  
##  <a name="getsplitimagelist"></a>CButton::GetSplitImageList  
 Извлекает [списка изображений](../../mfc/reference/cimagelist-class.md) для текущего управления SplitButton.  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_IMAGE` флаг, а затем отправляет, структуры в [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) описанное в Windows SDK. При возврате функция сообщения, этот метод извлекает список изображений из `himlGlyph` член структуры.  
  
##  <a name="getsplitinfo"></a>CButton::GetSplitInfo  
 Возвращает параметры, которые определяют, как средствами Windows текущего управления SplitButton.  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pInfo`|Указатель на [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры, который получает сведения о текущем управления SplitButton. Вызывающий объект отвечает за выделение структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод отправляет [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, которое описано в Windows SDK.  
  
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
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 При расширении управления SplitButton отображения раскрывающегося списка компонентами, такими как элемент управления список или элемент управления страничного навигатора. Этот метод возвращает ограничивающий прямоугольник, содержащий компонент раскрывающегося списка.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_SIZE` флаг, а затем отправляет, структуры в [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) описанное в Windows SDK. При возврате функция сообщения, этот метод возвращает прямоугольник, ограничивающий из `size` член структуры.  
  
##  <a name="getsplitstyle"></a>CButton::GetSplitStyle  
 Извлекает стили кнопок разбиение, определяющие текущего управления SplitButton.  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание стилей кнопок разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Стили кнопок разбиение укажите выравнивание, пропорций и графическом формате, с которым значок кнопки разделения средствами Windows.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_STYLE` флаг, а затем отправляет, структуры в [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) описанное в Windows SDK. При возврате функция сообщения, этот метод получает стили кнопок разбиение из `uSplitStyle` член структуры.  
  
##  <a name="getstate"></a>CButton::GetState  
 Возвращает состояние элемента управления button.  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Битовое поле, которое содержит комбинацию значений, которые указывают текущее состояние элемента управления button. В следующей таблице перечислены возможные значения.  
  
|Состояние кнопки|Значение|Описание|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|Начальное состояние.|  
|`BST_CHECKED`|0x0001|Установлен кнопке.|  
|`BST_INDETERMINATE`|0x0002|Состояние — неопределенное (возможно только если элемент управления button имеет три состояния).|  
|`BST_PUSHED`|0x0004|Кнопка нажата.|  
|`BST_FOCUS`|0x0008|Этот элемент управления имеет фокус.|  
  
### <a name="remarks"></a>Примечания  
 Элемент управления "Кнопка" с `BS_3STATE` или `BS_AUTO3STATE` стиль кнопки создает флажок для третьего состояния, которая называется неопределенное состояние. Неопределенное состояние указывает, что флажок не установлен и не снят флажок.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="gettextmargin"></a>CButton::GetTextMargin  
 Этот метод вызывается для получения текстового поля `CButton` объекта.  
  
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
 Эта функция-член эмулирует работу **BCM_GETTEXTMARGIN** сообщения, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) части пакета Windows SDK.  
  
##  <a name="setbitmap"></a>CButton::SetBitmap  
 Вызовите эту функцию-член для связывания новое растровое изображение с помощью кнопки.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `hBitmap`  
 Дескриптор растрового изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор растрового изображения, ранее назначенный данной кнопке.  
  
### <a name="remarks"></a>Примечания  
 Битовая карта будет автоматически помещается на лицевой стороне кнопки, по центру по умолчанию. Если растровое изображение слишком велико для кнопки, он будет обрезан по обеим сторонам. Можно выбрать другие параметры выравнивания, включая следующие:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), которая использует четыре растровые изображения на кнопке, `SetBitmap` использует только один растрового изображения на кнопке. При нажатии этой кнопки появляется точечный рисунок необходимо сдвинуть вниз и вправо.  
  
 Вы отвечаете за освобождая растрового изображения, когда вы завершили работу с ним.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="setbuttonstyle"></a>CButton::SetButtonStyle  
 Изменяет стиль кнопки.  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nStyle`  
 Указывает [кнопку стиль](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 `bRedraw`  
 Указывает, является ли кнопки перерисовку. Ненулевое значение — перерисовывает кнопку. Значение 0 не перерисовывает кнопки. По умолчанию перерисовке кнопки.  
  
### <a name="remarks"></a>Примечания  
 Используйте `GetButtonStyle` функция-член для извлечения стиль кнопки. Младшее слово стиля "Завершить" соответствует стилю кнопками.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="setcheck"></a>CButton::SetCheck  
 Устанавливает или сбрасывает состояние флажка "переключатель" или "флажок".  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 `nCheck`  
 Указывает состояние проверки. Этот параметр может иметь одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|**BST_UNCHECKED**|Задайте состояние кнопки, снимите флажок.|  
|**BST_CHECKED**|Задайте состояние кнопки для проверки.|  
|**BST_INDETERMINATE**|Значение неопределенное состояние кнопки. Это значение может использоваться только в том случае, если кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиля.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член не оказывает влияния на кнопки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="setcursor"></a>CButton::SetCursor  
 Вызовите эту функцию-член, чтобы связать новый курсор с кнопки.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Параметры  
 `hCursor`  
 Дескриптор курсора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсора, ранее назначенный данной кнопке.  
  
### <a name="remarks"></a>Примечания  
 Курсор автоматически помещается на лицевой стороне кнопки, по центру по умолчанию. Если курсор находится слишком велик для кнопки, он будет обрезан по обеим сторонам. Можно выбрать другие параметры выравнивания, включая следующие:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), которая использует четыре растровые изображения на кнопке, `SetCursor` использует только один курсор на кнопке. При нажатии кнопки курсор отображается смещения вниз и вправо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="setdropdownstate"></a>CButton::SetDropDownState  
 Задает состояние текущего управления SplitButton раскрывающегося списка.  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `fDropDown`|`true`Чтобы задать `BST_DROPDOWNPUSHED` состояние; в противном случае — `false`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления SplitButton имеет стиль `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON` и состоит из кнопки и стрелку раскрывающегося списка справа. Дополнительные сведения см. в разделе [стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb775951). Обычно когда пользователь щелкает стрелку раскрывающегося списка переходит в состояние раскрывающегося списка. Используйте этот метод, чтобы программно задать состояние раскрывающегося списка элемента управления. Стрелка раскрывающегося списка рисуется затененные для указания состояния.  
  
 Этот метод отправляет [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_splitButton`, который используется для программного доступа к управления SplitButton. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает состояние элемента управления SplitButton для указания, что помещается стрелку раскрывающегося списка.  
  
 [!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="setelevationrequired"></a>CButton::SetElevationRequired  
 Задает состояние текущего элемента управления кнопки для `elevation required`, которая необходима для элемента управления для отображения значка повышенных привилегий.  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `fElevationRequired`|`true`Чтобы задать `elevation required` состояние; в противном случае — `false`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления связями кнопку или команду требуются повышенные разрешения для выполнения действия, значение элемента управления `elevation required` состояние. Впоследствии появится значок щита управления учетных записей (UAC) в элементе управления. Дополнительные сведения см. в разделе «Контроль учетных записей пользователей» в [MSDN](http://go.microsoft.com/fwlink/linkid=18507).  
  
 Этот метод отправляет [BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979) сообщение, которое описано в Windows SDK.  
  
##  <a name="seticon"></a>CButton::SetIcon  
 Вызовите эту функцию-член для присоединения к ним новый значок кнопки.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 `hIcon`  
 Дескриптор значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значка, ранее назначенный данной кнопке.  
  
### <a name="remarks"></a>Примечания  
 Значок будет автоматически помещается на лицевой стороне кнопки, по центру по умолчанию. Если значок слишком велик для кнопки, он будет обрезан по обеим сторонам. Можно выбрать другие параметры выравнивания, включая следующие:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), которая использует четыре растровые изображения на кнопке, `SetIcon` использует только один значок на кнопке. При нажатии кнопки, значок отображается для сдвига вниз и вправо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="setimagelist"></a>CButton::SetImageList  
 Вызовите этот метод, чтобы задать список изображений `CButton` объекта.  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Параметры  
 `pbuttonImagelist`  
 Указатель на новый список изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_SETIMAGELIST** сообщения, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) части пакета Windows SDK.  
  
##  <a name="setnote"></a>CButton::SetNote  
 Задает текст для текущей команды управления ссылками.  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `lpszNote`|Указатель на строку Юникода, заданный как текст для команды управления ссылками.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_COMMANDLINK` или `BS_DEFCOMMANDLINK`.  
  
 Этот метод отправляет [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_cmdLink`, который используется для программного доступа к команды управления ссылками. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает текст для команды управления ссылками.  
  
 [!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="setsplitglyph"></a>CButton::SetSplitGlyph  
 Связывает указанный глифа с текущего управления SplitButton.  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `chGlyph`|Символ, указывающий глиф для использования в качестве разбиение стрелку раскрывающегося списка.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с помощью элементов управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Глиф является физическое представление символа в определенном шрифте. `chGlyph` Параметр не используется в качестве глифа, но вместо этого используется для выбора глиф из набора глифов, определенная системой. Глиф стрелку раскрывающегося списка по умолчанию задается символ "6" и напоминает знак Юникода, который ЧЕРНЫМ вниз ТРЕУГОЛЬНИК (U + 25BC).  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_GLYPH` флаг и `himlGlyph` член с `chGlyph` параметра, а затем отправляет, структуры в [ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в Windows SDK.  
  
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
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_IMAGE` флаг и `himlGlyph` член с `pSplitImageList` параметра, а затем отправляет, структуры в [ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в Windows SDK.  
  
##  <a name="setsplitinfo"></a>CButton::SetSplitInfo  
 Указывает параметры, которые определяют, как средствами Windows текущего управления SplitButton.  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pInfo`|Указатель на [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура, определяющая текущего управления SplitButton.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Этот метод отправляет [BCM_SETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775981) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_splitButton`, который используется для программного доступа к управления SplitButton.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода изменяется глифа, используемый для разбиения стрелку раскрывающегося списка. В примере подставляются глифа направленный вверх треугольник глифа направленный вниз треугольник по умолчанию. Значок, отображаемый зависит от символ, указанный в `himlGlyph` членом `BUTTON_SPLITINFO` структуры. Глиф направленный вниз треугольник указывается символ "6"и глиф направленный вверх треугольник указан символ ' 5'. Сравнение см. в разделе удобный метод, [CButton::SetSplitGlyph](#setsplitglyph).  
  
 [!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
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
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 При расширении управления SplitButton отображения раскрывающегося списка компонентами, такими как элемент управления список или элемент управления страничного навигатора. Этот метод задает размер ограничивающего прямоугольника, содержащего компонент раскрывающегося списка.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_SIZE` флаг и `size` член с `pSize` параметра, а затем отправляет, структуры в [ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_splitButton`, который используется для программного доступа к управления SplitButton. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода удваивается объем разбиение стрелку раскрывающегося списка.  
  
 [!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="setsplitstyle"></a>CButton::SetSplitStyle  
 Задает стиль текущего управления SplitButton.  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `uSplitStyle`|Побитовое сочетание стилей кнопок разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать только с элементами управления, имеющих стиль кнопки `BS_SPLITBUTTON` или `BS_DEFSPLITBUTTON`.  
  
 Стили кнопок разбиение укажите выравнивание, пропорций и графическом формате, с которым значок кнопки разделения средствами Windows. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структуры.  
  
 Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) структура с `BCSIF_STYLE` флаг и `uSplitStyle` член с `uSplitStyle` параметра, а затем отправляет, структуры в [ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) сообщение, описанное в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_splitButton`, который используется для программного доступа к управления SplitButton.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает стиль разбиение стрелку раскрывающегося списка. `BCSS_ALIGNLEFT` Отображение стрелку слева от кнопки и `BCSS_STRETCH` стиль сохраняет пропорции стрелку раскрывающегося списка, при изменении размера кнопки.  
  
 [!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="setstate"></a>CButton::SetState  
 Указывает, будет выделен элемент управления button или нет.  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Параметры  
 *bHighlight*  
 Указывает, будет ли отображаться кнопки. Ненулевое значение выделяет кнопки. значение 0 удаляет все выделение.  
  
### <a name="remarks"></a>Примечания  
 Выделение влияет на внешнее элемента управления button. Он не оказывает влияния на состояние флажка "переключатель" или "флажок".  
  
 Элемент управления button автоматически выделяется, когда пользователь нажимает и удерживает левой кнопки мыши. Выделение удаляется, когда пользователь отпускает кнопку мыши.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="settextmargin"></a>CButton::SetTextMargin  
 Вызовите этот метод, чтобы задать размер текстового поля `CButton` объекта.  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Параметры  
 `pmargin`  
 Указатель на поле новый текст.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу **BCM_SETTEXTMARGIN** сообщения, как описано в [кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775943) части пакета Windows SDK.  
  
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
 [Класс CDialog](../../mfc/reference/cdialog-class.md)
