---
title: "CStatusBarCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CStatusBarCtrl
- CStatusBarCtrl class
- status bar controls
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
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
ms.openlocfilehash: 619fb88b96f60ab2dc0911cb8ea0b66574ea4287
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "индикатор статуса" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Создает объект `CStatusBarCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](#create)|Создает элемент управления строка состояния и присоединяет его к `CStatusBarCtrl` объекта.|  
|[CStatusBarCtrl::CreateEx](#createex)|Создает элемент управления строка состояния с указанным расширенные стили Windows и присоединяет его к `CStatusBarCtrl` объекта.|  
|[CStatusBarCtrl::DrawItem](#drawitem)|Вызывается при изменении внешнего вида панели управления рисование владельцем состояние изменится.|  
|[CStatusBarCtrl::GetBorders](#getborders)|Извлекает текущей ширины горизонтальной и вертикальной границы элемента управления строки состояния.|  
|[CStatusBarCtrl::GetIcon](#geticon)|Получает значок для элемента (также известный как панель) строки состояния.|  
|[CStatusBarCtrl::GetParts](#getparts)|Получает число элементов в элемент управления строки состояния.|  
|[CStatusBarCtrl::GetRect](#getrect)|Возвращает прямоугольник, ограничивающий части строки состояния.|  
|[CStatusBarCtrl::GetText](#gettext)|Извлекает текст из заданной части строки состояния.|  
|[CStatusBarCtrl::GetTextLength](#gettextlength)|Получение длины в символы текста из заданной части строки состояния.|  
|[CStatusBarCtrl::GetTipText](#gettiptext)|Извлекает текст всплывающей подсказки для панели в строке состояния.|  
|[CStatusBarCtrl::IsSimple](#issimple)|Проверяет состояние элемента управления окна, чтобы определить его в простом режиме.|  
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Задает цвет фона в строке состояния.|  
|[CStatusBarCtrl::SetIcon](#seticon)|Задает значок для области, в строке состояния.|  
|[CStatusBarCtrl::SetMinHeight](#setminheight)|Задает минимальную высоту состояния панели область рисования элемента управления.|  
|[CStatusBarCtrl::SetParts](#setparts)|Задает число частей в состоянии элемента управления и координаты по правому краю каждой части панели.|  
|[CStatusBarCtrl::SetSimple](#setsimple)|Указывает, отображает простой текст строки состояния или отображает все части элемента управления, заданные предыдущего вызова `SetParts`.|  
|[CStatusBarCtrl::SetText](#settext)|Задает текст в указанной части элемента управления "Строка состояния".|  
|[CStatusBarCtrl::SetTipText](#settiptext)|Задает текст всплывающей подсказки для области в строке состояния.|  
  
## <a name="remarks"></a>Примечания  
 «Элемент управления строки состояния» является окном горизонтальной, обычно отображается в нижней части родительского окна, в которой выводятся различные сведения о состоянии приложения. Элемент управления строки состояния можно разделить на части, чтобы отобразить несколько типов сведений.  
  
 Этот элемент управления (и, следовательно, `CStatusBarCtrl` класса) доступны только для программы, запущенные в Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Дополнительные сведения об использовании `CStatusBarCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CStatusBarCtrl с помощью](../../mfc/using-cstatusbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-namecreatea--cstatusbarctrlcreate"></a><a name="create"></a>CStatusBarCtrl::Create  
 Создает элемент управления строка состояния и присоединяет его к `CStatusBarCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль управления строкой состояния. Примените любое сочетание состояния панели управления стилей в [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Этот параметр необходимо указывать **WS_CHILD** стиль. Она также должна включать **WS_VISIBLE** стиль.  
  
 `rect`  
 Задает размер и положение управления строкой состояния. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает состояние панели родительского окна элемента управления, обычно `CDialog`. Оно не должно быть **значение NULL.**  
  
 `nID`  
 Указывает идентификатор управления строкой состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Создании `CStatusBarCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления строки состояния и присоединяет его к `CStatusBarCtrl` объекта.  
  
 По умолчанию окна состояния располагается в нижней части родительского окна, но можно указать `CCS_TOP` стиль, чтобы они появились в верхней части клиентской области родительского окна. Можно указать **SBARS_SIZEGRIP** стиль можно включить захват для изменения размера в правом конце в окне состояния. Объединение `CCS_TOP` и **SBARS_SIZEGRIP** стили не рекомендуется, поскольку захвата для изменения размера не работает, несмотря на то, что система отображает его в окне состояния.  
  
 Чтобы создать строку состояния с расширенные стили окна, вызовите [CStatusBarCtrl::CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#1;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]  
  
##  <a name="a-namecreateexa--cstatusbarctrlcreateex"></a><a name="createex"></a>CStatusBarCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CStatusBarCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль управления строкой состояния. Примените любое сочетание состояния панели управления стилей в [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Этот параметр необходимо указывать **WS_CHILD** стиль. Она также должна включать **WS_VISIBLE** стиль.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="a-namecstatusbarctrla--cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a>CStatusBarCtrl::CStatusBarCtrl  
 Создает объект `CStatusBarCtrl`.  
  
```  
CStatusBarCtrl();
```  
  
##  <a name="a-namedrawitema--cstatusbarctrldrawitem"></a><a name="drawitem"></a>CStatusBarCtrl::DrawItem  
 Вызывается инфраструктурой при изменении внешнего вида панели управления рисование владельцем состояние изменится.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Длинный указатель [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисование владельцем `CStatusBarCtrl` объекта.  
  
 Приложение должно восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct` перед этим членом завершении функции.  
  
##  <a name="a-namegetbordersa--cstatusbarctrlgetborders"></a><a name="getborders"></a>CStatusBarCtrl::GetBorders  
 Извлекает управления строкой состояния текущей ширины горизонтальной и вертикальной границы и расстояние между прямоугольниками.  
  
```  
BOOL GetBorders(int* pBorders) const;  
  
BOOL GetBorders(
    int& nHorz,  
    int& nVert,  
    int& nSpacing) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pBorders*  
 Адрес целочисленный массив с тремя элементами. Первый элемент получает ширину горизонтальной границы, второй Получает ширину вертикальной границы и третий Получает ширину границы между прямоугольниками.  
  
 *nHorz*  
 Ссылка на целое число, Получает ширину горизонтальной границы.  
  
 *Преобразование*  
 Ссылка на целое число, которое получает ширину вертикальной границы.  
  
 *nSpacing*  
 Ссылку на целое число, которое получает ширину границы между прямоугольниками.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эти границы определяют расстояние между внешней границей элемента управления и прямоугольников, содержащих текст в элементе управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#2;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]  
  
##  <a name="a-namegeticona--cstatusbarctrlgeticon"></a><a name="geticon"></a>CStatusBarCtrl::GetIcon  
 Получает значок для элемента (также известный как панель) строки состояния.  
  
```  
HICON GetIcon(int iPart) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iPart`|Отсчитываемый от нуля индекс элемента, содержащего значок, который требуется получить. Если этот параметр имеет значение -1, в строке состояния предполагается равным строке состояния простой режим.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значка, если метод успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [SB_GETICON](http://msdn.microsoft.com/library/windows/desktop/bb760744) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Элемент управления строки состояния состоит из ряда панелей вывода текста, которые также называются частей. Дополнительные сведения о строке состояния см. в разделе [реализация строки состояния в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [Установка режима объекта CStatusBarCtrl](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_statusBar`, который используется для доступа к текущей строки состояния. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода копирует значка на две области строки состояния. В предыдущем разделе примера кода содержит три панели строки состояния, а затем добавить значок в первой области. В этом примере извлекает значок из первой области и затем добавляет его в область второй и третий.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]  
  
##  <a name="a-namegetpartsa--cstatusbarctrlgetparts"></a><a name="getparts"></a>CStatusBarCtrl::GetParts  
 Получает число элементов в элемент управления строки состояния.  
  
```  
int GetParts(
    int nParts,  
    int* pParts) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nParts`  
 Число частей, для которого необходимо получить координаты. Если этот параметр больше, чем число элементов в элементе управления, сообщение извлекает координаты только существующих частей.  
  
 *pParts*  
 Адрес массива целых чисел с одинаковое количество элементов, как номер части, указанные в `nParts`. Каждый элемент в массиве получает клиентских координат правой границы соответствующей части. Если элемент имеет значение – 1, расширяет положение правой границы для этой части к правому краю строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число частей в элемент управления, в случае успешного выполнения или в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член также Получает координату правого края на заданное число частей.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#3;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]  
  
##  <a name="a-namegetrecta--cstatusbarctrlgetrect"></a><a name="getrect"></a>CStatusBarCtrl::GetRect  
 Возвращает прямоугольник, ограничивающий части строки состояния.  
  
```  
BOOL GetRect(
    int nPane,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nPane`  
 Отсчитываемый от нуля индекс части которого ограничивающий прямоугольник для извлечения.  
  
 `lpRect`  
 Адрес [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает ограничивающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#4;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]  
  
##  <a name="a-namegettexta--cstatusbarctrlgettext"></a><a name="gettext"></a>CStatusBarCtrl::GetText  
 Извлекает текст из заданной части строки состояния.  
  
```  
CString GetText(
    int nPane,  
    int* pType = NULL) const;  
  
int GetText(
    LPCTSTR lpszText,  
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Адрес буфера, который получает текст. Этот параметр является строка, заканчивающаяся нулем.  
  
 `nPane`  
 Отсчитываемый от нуля индекс части, из которого извлекается текст.  
  
 `pType`  
 Указатель на целое число, которое получает сведения о типе. Тип может быть одно из следующих значений:  
  
- **0** текст рисуется граница отображаться ниже, чем плоскости в строке состояния.  
  
- `SBT_NOBORDERS`Текст отображается без границ.  
  
- `SBT_POPOUT`Текст рисуется граница отображаться выше, чем плоскости в строке состояния.  
  
- `SBT_OWNERDRAW`Если текст имеет `SBT_OWNERDRAW` тип, графического `pType` получает это сообщение и возвращает 32-разрядное значение, связанное с текста вместо типа длины и операции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина в символах, текста или [CString](../../atl-mfc-shared/reference/cstringt-class.md) содержащий текст текущего.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#5;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]  
  
##  <a name="a-namegettextlengtha--cstatusbarctrlgettextlength"></a><a name="gettextlength"></a>CStatusBarCtrl::GetTextLength  
 Получает длину в символах текста из заданной части строки состояния.  
  
```  
int GetTextLength(
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nPane`  
 Отсчитываемый от нуля индекс части, из которого извлекается текст.  
  
 `pType`  
 Указатель на целое число, которое получает сведения о типе. Тип может быть одно из следующих значений:  
  
- **0** текст рисуется граница отображаться ниже, чем плоскости в строке состояния.  
  
- `SBT_NOBORDERS`Текст отображается без границ.  
  
- `SBT_OWNERDRAW`Текст рисуется родительским окном.  
  
- `SBT_POPOUT`Текст рисуется граница отображаться выше, чем плоскости в строке состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина в символах текста.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl №&6;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]  
  
##  <a name="a-namegettiptexta--cstatusbarctrlgettiptext"></a><a name="gettiptext"></a>CStatusBarCtrl::GetTipText  
 Извлекает текст всплывающей подсказки для панели в строке состояния.  
  
```  
CString GetTipText(int nPane) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nPane`  
 Отсчитываемый от нуля индекс панели строки состояния для получения текста подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий текст для использования в подсказке.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [SB_GETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760751), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#7;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]  
  
##  <a name="a-nameissimplea--cstatusbarctrlissimple"></a><a name="issimple"></a>CStatusBarCtrl::IsSimple  
 Проверяет состояние элемента управления окна, чтобы определить его в простом режиме.  
  
```  
BOOL IsSimple() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления окно состояния в простом режиме; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [SB_ISSIMPLE](http://msdn.microsoft.com/library/windows/desktop/bb760753), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbkcolora--cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a>CStatusBarCtrl::SetBkColor  
 Задает цвет фона в строке состояния.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Параметры  
 `cr`  
 **COLORREF** значение, которое указывает новый цвет фона. Укажите `CLR_DEFAULT` значение заставить строку состояния, чтобы использовать цвет фона по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее на предыдущий цвет фона по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [SB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760754), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl №&8;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]  
  
##  <a name="a-nameseticona--cstatusbarctrlseticon"></a><a name="seticon"></a>CStatusBarCtrl::SetIcon  
 Задает значок для области, в строке состояния.  
  
```  
BOOL SetIcon(
    int nPane,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 `nPane`  
 Отсчитываемый от нуля индекс панели, который получит этот значок. Если этот параметр имеет значение -1, в строке состояния предполагается равным строку состояния простой.  
  
 `hIcon`  
 Значок, чтобы задать дескриптор. Если это значение равно **NULL**, значок удаляется из части.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [SB_SETICON](http://msdn.microsoft.com/library/windows/desktop/bb760755), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CStatusBarCtrl::SetBkColor](#setbkcolor).  
  
##  <a name="a-namesetminheighta--cstatusbarctrlsetminheight"></a><a name="setminheight"></a>CStatusBarCtrl::SetMinHeight  
 Задает минимальную высоту состояния панели область рисования элемента управления.  
  
```  
void SetMinHeight(int nMin);
```  
  
### <a name="parameters"></a>Параметры  
 `nMin`  
 Минимальная высота в точках управления.  
  
### <a name="remarks"></a>Примечания  
 Минимальная высота является суммой `nMin` и дважды ширина в пикселях вертикальной границы строки состояния.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl №&9;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]  
  
##  <a name="a-namesetpartsa--cstatusbarctrlsetparts"></a><a name="setparts"></a>CStatusBarCtrl::SetParts  
 Задает число частей в состоянии элемента управления и координаты по правому краю каждой части панели.  
  
```  
BOOL SetParts(
    int nParts,  
    int* pWidths);
```  
  
### <a name="parameters"></a>Параметры  
 `nParts`  
 Число частей для задания. Число частей не может быть больше 255.  
  
 *pWidths*  
 Адрес массива целых чисел, имеющая одинаковое количество элементов в качестве части, указанные в `nParts`. Каждый элемент массива указывает положение в клиентских координатах, правого края соответствующей частью. Если элемент — 1, положение правой границы для данной части расширяет к правому краю элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#10;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]  
  
##  <a name="a-namesetsimplea--cstatusbarctrlsetsimple"></a><a name="setsimple"></a>CStatusBarCtrl::SetSimple  
 Указывает, отображает простой текст строки состояния или отображает все части элемента управления, заданные предыдущего вызова [SetParts](#setparts).  
  
```  
BOOL SetSimple(BOOL bSimple = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSimple`  
 Флаг тип отображения. Если этот параметр равен `TRUE`, элемент управления отображает простой текст; Если это `FALSE`, он отображает несколько частей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение изменяет строки состояния с непростой простой или наоборот, система немедленно обновит элемент управления.  
  
##  <a name="a-namesettexta--cstatusbarctrlsettext"></a><a name="settext"></a>CStatusBarCtrl::SetText  
 Задает текст в указанной части элемента управления "Строка состояния".  
  
```  
BOOL SetText(
    LPCTSTR lpszText,  
    int nPane,  
    int nType);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Адрес в виде оканчивающейся нулем строки, в которой указан необходимый текст. Если значением `nType` является `SBT_OWNERDRAW`, `lpszText` представляет собой 32 бита данных.  
  
 `nPane`  
 Отсчитываемый от нуля индекс настраиваемой части. Если это значение равно 255, строка состояния считается простым элементом управления, состоящим из одной части.  
  
 `nType`  
 Тип операции отрисовки. В разделе [SB_SETTEXT сообщения](http://msdn.microsoft.com/library/bb760758\(vs.85\).aspx) список возможных значений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Сообщение объявляет недействительной измененную часть элемента управления, и, когда он в следующий раз получает сообщение `WM_PAINT`, отображается новый текст.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&11;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]  
  
##  <a name="a-namesettiptexta--cstatusbarctrlsettiptext"></a><a name="settiptext"></a>CStatusBarCtrl::SetTipText  
 Задает текст всплывающей подсказки для области в строке состояния.  
  
```  
void SetTipText(
    int nPane,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Параметры  
 `nPane`  
 Отсчитываемый от нуля индекс панели строки состояния для получения текста подсказки.  
  
 *pszTipText*  
 Указатель на строку, содержащую текст подсказки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [SB_SETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760759), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#12;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl-класс](../../mfc/reference/ctoolbarctrl-class.md)

