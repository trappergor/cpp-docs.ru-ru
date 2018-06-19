---
title: CComboBoxEx-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
dev_langs:
- C++
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd7d2c5bbd3445e604620dc1f23f45004b7a3b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358295"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx-класс
Расширяет элемент управления "поле со списком", предоставляя поддержку списков изображений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Создает объект `CComboBoxEx`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|Создает поле со списком и прикрепляет его к `CComboBoxEx` объекта.|  
|[CComboBoxEx::CreateEx](#createex)|Создает поле со списком с указанным расширенные стили Windows и прикрепляет его к **ComboBoxEx** объекта.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|Удаляет элемент из **ComboBoxEx** управления.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Извлекает указатель на дочерний элемент управления ComboBox.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Извлекает дескриптор часть элемента управления Правка с **ComboBoxEx** управления.|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, которые используются для **ComboBoxEx** управления.|  
|[CComboBoxEx::GetImageList](#getimagelist)|Извлекает указатель на список изображений, назначенный **ComboBoxEx** управления.|  
|[CComboBoxEx::GetItem](#getitem)|Получение сведений об элементе для заданного **ComboBoxEx** элемента.|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Определяет, если пользователь изменил содержимое **ComboBoxEx** редактирование элемента управления вводом.|  
|[CComboBoxEx::InsertItem](#insertitem)|Вставляет новый элемент в **ComboBoxEx** управления.|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили в **ComboBoxEx** управления.|  
|[CComboBoxEx::SetImageList](#setimagelist)|Задает список изображений для **ComboBoxEx** управления.|  
|[CComboBoxEx::SetItem](#setitem)|Задает атрибуты для элемента в **ComboBoxEx** управления.|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Задает поле визуальный стиль Расширенное поле со списком.|  
  
## <a name="remarks"></a>Примечания  
 С помощью `CComboBoxEx` создать поле со списком элементов управления, больше не нужно реализовать собственный образ код отрисовки. Вместо этого используйте `CComboBoxEx` для доступа к изображений из списка изображений.  
  
## <a name="image-list-support"></a>Поддержка списков изображений  
 В поле со списком стандартных владельцем поле со списком отвечает за рисование изображения путем создания как элемент управления рисуемого владельцем поле со списком. При использовании `CComboBoxEx`, вам не нужно задавать стили рисования **CBS_OWNERDRAWFIXED** и **CBS_HASSTRINGS** так, как они применяются. В противном случае необходимо написать код для выполнения операции рисования. Объект `CComboBoxEx` элемент управления поддерживает до трех изображения каждого элемента: один для выбранного состояния, один для невыбранном состоянии и один для наложения изображения.  
  
## <a name="styles"></a>Стили  
 `CComboBoxEx` поддерживает стили **CBS_SIMPLE**, **CBS_DROPDOWN**, **CBS_DROPDOWNLIST**, и **WS_CHILD**. Все стили, передаваемого при создании окна игнорируются элементом управления. После создания окна другие поля со списком можно предоставить стили окна путем вызова `CComboBoxEx` функции-члена [SetExtendedStyle](#setextendedstyle). Эти стили можно:  
  
-   Набор операций поиска в списке, чтобы учитывать регистр.  
  
-   Создать поле со списком, использующий косой черты («/»), обратной косой черты ("\\") и период (".") символов в качестве разделителей слов. Это позволить пользователям переходить из word для word с помощью сочетания клавиш CTRL + стрелка.  
  
-   Задайте поле со списком управления поле для отображения или не выводит изображение. Если изображение не отображается, в поле со списком можно удалить отступ текста, который допустим для изображения.  
  
-   Создайте узкое поле со списком, включая изменения размера, он отсекает шире поле со списком, которые она содержит.  
  
 Эти флаги стиль описаны далее в [использование CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="item-retention-and-callback-item-attributes"></a>Элемент хранения и атрибуты элементов обратного вызова  
 Сведения об элементе, таких как индексы элементов и изображений, необходимые значения отступов и текстовые строки хранятся в структуре Win32 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746), как описано в Windows SDK. Структура также содержит члены, соответствующие флаги обратного вызова.  
  
 Подробные Общие сведения см. в разделе [использование CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx  
 Вызовите эту функцию-член для создания `CComboBoxEx` объекта.  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>  CComboBoxEx::Create  
 Создает поле со списком и прикрепляет его к `CComboBoxEx` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает сочетание стили полей со списком применяются к полю со списком. В разделе **примечания** ниже дополнительные сведения о стилях.  
  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которая является положение и размер комбинированного окна.  
  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который является родительским окном списком (обычно `CDialog`). Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создание `CComboBoxEx` объекта в два этапа:  
  
1.  Вызовите [CComboBoxEx](#ccomboboxex) для создания `CComboBoxEx` объекта.  
  
2.  Вызовите эту функцию-член, который создает расширенные поле со списком Windows и прикрепляет его к `CComboBoxEx` объекта.  
  
 При вызове **создать**, MFC инициализирует стандартных элементов управления.  
  
 При создании поле со списком, можно указать одно или все следующие стили полей со списками:  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 Все стили, передаваемого при создании окна учитываются. **ComboBoxEx** управления также поддерживает расширенные стили, которые предоставляют дополнительные возможности. Эти стили описаны в [ComboBoxEx управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb775742), в Windows SDK. Установка этих стилей путем вызова [SetExtendedStyle](#setextendedstyle).  
  
 Если вы хотите использовать с элементом управления windows расширенных стилей, вызовите [CreateEx](#createex) вместо **создать**.  
  
##  <a name="createex"></a>  CComboBoxEx::CreateEx  
 Эта функция вызывается для создания расширенных поле со списком (дочернего окна) и связать его с `CComboBoxEx` объекта.  
  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 `dwStyle`  
 Стиль элемента управления поля со списком. В разделе [создать](#create) список стилей.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо **создать** для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
 `CreateEx` Создает элемент управления с расширенные стили Windows, указанные для `dwExStyle`. Необходимо задать расширенные стили конкретных Расширенное поле со списком управления с помощью [SetExtendedStyle](#setextendedstyle). Например, использовать `CreateEx` задание стилей, таких как **WS_EX_CONTEXTHELP**, но использовать `SetExtendedStyle` задание стилей, таких как **CBES_EX_CASESENSITIVE**. Дополнительные сведения см. в разделе стили, описанные в разделе [стилей расширенных элементов управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775742) в Windows SDK.  
  
##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem  
 Удаляет элемент из **ComboBoxEx** управления.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `iIndex`  
 Отсчитываемый от нуля индекс удаляемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, оставшихся в элементе управления. Если `iIndex` является недопустимым, функция возвращает **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768), как описано в Windows SDK. При вызове DeleteItem, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений с **CBEN_DELETEITEM** будет отправлено уведомление для родительского окна.  
  
##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl  
 Вызовите эту функцию-член для получения указателя на поле со списком в `CComboBoxEx` объекта.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `CComboBox`.  
  
### <a name="remarks"></a>Примечания  
 `CComboBoxEx` Управления состоит из родительского окна, который инкапсулирует `CComboBox`.  
  
 `CComboBox` Объекта, на который указывает возвращаемое значение является временным и удаляются во время следующей обработки простоя.  
  
##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl  
 Вызовите эту функцию-член для получения указателя на элемент управления для редактирования для поля со списком.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CEdit](../../mfc/reference/cedit-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Объект `CComboBoxEx` управления использует поле редактирования при его создании с **CBS_DROPDOWN** стиля.  
  
 `CEdit` Объекта, на который указывает возвращаемое значение является временным и удаляются во время следующей обработки простоя.  
  
##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle  
 Вызовите эту функцию-член для получения расширенных стилей, используемых для `CComboBoxEx` элемента управления.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `DWORD` Значение, которое содержит расширенные стили, используемые для элемента управления полем со списком.  
  
### <a name="remarks"></a>Примечания  
 В разделе [стилей расширенных элементов управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775742) в Windows SDK, Дополнительные сведения об этих стилях.  
  
##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList  
 Вызовите эту функцию-член для получения указателя на список изображений, используемых `CComboBoxEx` элемента управления.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта. Если происходит сбой, эта функция-член возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 `CImageList` Объекта, на который указывает возвращаемое значение является временным и удаляются во время следующей обработки простоя.  
  
##  <a name="getitem"></a>  CComboBoxEx::GetItem  
 Получение сведений об элементе для заданного **ComboBoxEx** элемента.  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pCBItem`  
 Указатель на [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) структуру, которая будет получать сведения об элементе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779), как описано в Windows SDK.  
  
##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged  
 Определяет, если пользователь изменил содержимое **ComboBoxEx** редактирование элемента управления вводом.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь вводит в поле ввода элемента управления; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782), как описано в Windows SDK.  
  
##  <a name="insertitem"></a>  CComboBoxEx::InsertItem  
 Вставляет новый элемент в **ComboBoxEx** управления.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pCBItem`  
 Указатель на [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) структуру, которая будет получать сведения об элементе. Эта структура содержит значения флага обратного вызова для элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс, в которую был вставлен новый элемент, в случае успешного выполнения; в противном случае значение -1.  
  
### <a name="remarks"></a>Примечания  
 При вызове `InsertItem`, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений с [CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764) будет отправлено уведомление для родительского окна.  
  
##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle  
 Вызовите эту функцию-член для задания расширенных стилей, используемых для расширенного управления списком.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExMask`  
 Объект `DWORD` значение, указывающее, какие стили в `dwExStyles` , могут быть затронуты. Расширенные стили в `dwExMask` будет изменен. Все стили будут сохранены как есть. Если этот параметр равен нулю, то все стили в `dwExStyles` будут затронуты.  
  
 `dwExStyles`  
 Объект `DWORD` значение, которое содержит поле со списком управления расширенные стили, чтобы задать для элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` значение, которое содержит расширенные стили, которые ранее использовались для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [стилей расширенных элементов управления ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775742) в Windows SDK, Дополнительные сведения об этих стилях.  
  
 Чтобы создать поле со списком расширенных элементов управления с помощью windows расширенных стилей, используйте [CreateEx](#createex).  
  
##  <a name="setimagelist"></a>  CComboBoxEx::SetImageList  
 Задает список изображений для **ComboBoxEx** управления.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объектом, содержащим изображения для использования в `CComboBoxEx` элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объектом, содержащим изображения, ранее используемые `CComboBoxEx` элемента управления. **Значение NULL** Если список изображений не было установлено ранее.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787), как описано в Windows SDK. Если изменить высоту элемента управления по умолчанию, вызовите функцию Win32 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) для изменения размеров элемента управления, после вызова метода `SetImageList`, или он не будет отображаться должным образом.  
  
 `CImageList` Объекта, на который указывает возвращаемое значение является временным и удаляются во время следующей обработки простоя.  
  
##  <a name="setitem"></a>  CComboBoxEx::SetItem  
 Задает атрибуты для элемента в **ComboBoxEx** управления.  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pCBItem`  
 Указатель на [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) структуру, которая будет получать сведения об элементе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788), как описано в Windows SDK.  
  
##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme  
 Задает поле визуальный стиль Расширенное поле со списком.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 `pszSubAppName`  
 Указатель на строку Юникода, содержит визуальный стиль Расширенное поле со списком поле для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) сообщения, как описано в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCIE](../../visual-cpp-samples.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CComboBox](../../mfc/reference/ccombobox-class.md)
