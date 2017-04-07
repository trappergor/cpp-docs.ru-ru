---
title: "CComboBoxEx-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- extended combo boxes, CComboBoxEx class
- Windows common controls [C++], extended combo boxes
- common controls [C++], extended combo boxes
- combo boxes [C++], CComboBoxEx class
- Internet Explorer 4.0 common controls
- CComboBoxEx class
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
caps.latest.revision: 26
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
ms.openlocfilehash: e88ed701111b49e3a5d3b32868bfad8e77206086
ms.lasthandoff: 02/24/2017

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
|[CComboBoxEx::Create](#create)|Создает поле со списком и присоединяет его к `CComboBoxEx` объекта.|  
|[CComboBoxEx::CreateEx](#createex)|Создает поле со списком с указанным расширенные стили Windows и присоединяет его к **ComboBoxEx** объекта.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|Удаляет элемент из **ComboBoxEx** управления.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Извлекает указатель на дочерний элемент управления поля со списком.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Получает дескриптор в область редактирования элемента управления **ComboBoxEx** управления.|  
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
 С помощью `CComboBoxEx` для создания элементов управления со списком, больше не требуется реализовать собственный образ, код. Вместо этого используйте `CComboBoxEx` образы доступа из списка изображений.  
  
## <a name="image-list-support"></a>Поддержка списков изображений  
 В поле со списком стандартных владельца поле со списком отвечает за рисование изображения, создавая поле со списком как элемент управления рисование владельцем. При использовании `CComboBoxEx`, необходимо задать стили рисования **CBS_OWNERDRAWFIXED** и **CBS_HASSTRINGS** так, как они применяются. В противном случае необходимо написать код для выполнения операции рисования. A `CComboBoxEx` управления поддерживает до трех изображения каждого элемента: один для выбранного состояния, один для невыбранном состоянии и один для наложения изображения.  
  
## <a name="styles"></a>Стили  
 `CComboBoxEx`поддерживает стили **CBS_SIMPLE**, **CBS_DROPDOWN**, **CBS_DROPDOWNLIST**, и **WS_CHILD**. С помощью элемента управления игнорируются все другие стили, переданный при создании окна. После создания окна другие поля со списком можно предоставить стили окна путем вызова `CComboBoxEx` функции-члена [SetExtendedStyle](#setextendedstyle). Эти стили можно:  
  
-   Набор операций поиска в списке, чтобы быть с учетом регистра.  
  
-   Создать поле со списком, использующий косой черты ('/'), обратной косой черты ("\\") и период (".") символов в качестве разделителей слов. Это позволить пользователям переходить из word в word с помощью сочетания клавиш CTRL + стрелка.  
  
-   Задайте поле со списком управления поле для отображения или не выводит изображение. Если изображение не отображается, поле со списком можно удалить отступ текста, который допустим для изображения.  
  
-   Создайте узкий поле со списком, включая изменение размеров, она обрезает шире поле со списком, содержащихся в нем.  
  
 Они описаны далее в этих флагов стилей [CComboBoxEx с помощью](../../mfc/using-ccomboboxex.md).  
  
## <a name="item-retention-and-callback-item-attributes"></a>Элемент хранения и обратного вызова элемента атрибутов  
 Сведения об элементе, например индексы элементов и изображений, значения отступов и текстовые строки хранятся в структуре Win32 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Структура также содержит элементы, соответствующие флаги обратного вызова.  
  
 Подробные концептуальные сведения см. в разделе [CComboBoxEx с помощью](../../mfc/using-ccomboboxex.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>CComboBoxEx::CComboBoxEx  
 Вызов этой функции-члена для создания `CComboBoxEx` объекта.  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>CComboBoxEx::Create  
 Создает поле со списком и присоединяет его к `CComboBoxEx` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает сочетание стили поле со списком, примененные к поле со списком. В разделе **примечания** ниже дополнительные сведения о стилях.  
  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которая является положение и размер поля со списком.  
  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который является родительским окном поле со списком (обычно `CDialog`). Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создание `CComboBoxEx` объекта в два этапа:  
  
1.  Вызов [CComboBoxEx](#ccomboboxex) для создания `CComboBoxEx` объекта.  
  
2.  Вызовите эту функцию-член, который расширенной поле со списком Windows создает и присоединяет его к `CComboBoxEx` объекта.  
  
 При вызове **создать**, MFC инициализирует стандартных элементов управления.  
  
 При создании поле со списком, можно указать одно или все следующие стили поле со списком:  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 Игнорируются все другие стили, переданный при создании окна. **ComboBoxEx** управления также поддерживает расширенные стили, которые предоставляют дополнительные возможности. Эти стили, описаны в [ComboBoxEx управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb775742)в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Установка этих стилей путем вызова [SetExtendedStyle](#setextendedstyle).  
  
 Если вы хотите использовать с элементом управления windows расширенные стили, вызвать [CreateEx](#createex) вместо **создать**.  
  
##  <a name="createex"></a>CComboBoxEx::CreateEx  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Стиль элемента управления поля со списком. В разделе [создать](#create) список стилей.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо **создать** для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
 `CreateEx`Создает элемент управления с помощью расширенных стилей Windows, заданные `dwExStyle`. Необходимо задать в расширенные стили определенных Расширенное поле со списком элемента управления с помощью [SetExtendedStyle](#setextendedstyle). Например, используйте `CreateEx` установка стилей, таких как **WS_EX_CONTEXTHELP**, но использовать `SetExtendedStyle` установка стилей, таких как **CBES_EX_CASESENSITIVE**. Дополнительные сведения см. в разделе стили, описаны в разделе [ComboBoxEx управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb775742) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deleteitem"></a>CComboBoxEx::DeleteItem  
 Удаляет элемент из **ComboBoxEx** управления.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `iIndex`  
 Отсчитываемый от нуля индекс удаляемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов, оставшихся в элементе управления. Если `iIndex` является недопустимым, функция возвращает **CB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. При вызове DeleteItem, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений с **CBEN_DELETEITEM** отправляется уведомление родительского окна.  
  
##  <a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl  
 Вызовите эту функцию-член для получения указателя на поле со списком в `CComboBoxEx` объекта.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `CComboBox`.  
  
### <a name="remarks"></a>Примечания  
 `CComboBoxEx` Управления состоит из родительского окна, который инкапсулирует `CComboBox`.  
  
 `CComboBox` Объект, на который указывает возвращаемое значение является временным и уничтожается во время следующей обработки времени простоя.  
  
##  <a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl  
 Вызовите эту функцию-член для получения указателя на элемент управления поля ввода для поля со списком.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CEdit](../../mfc/reference/cedit-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Объект `CComboBoxEx` элемент управления использует поле ввода, когда он создается с **CBS_DROPDOWN** стиль.  
  
 `CEdit` Объект, на который указывает возвращаемое значение является временным и уничтожается во время следующей обработки времени простоя.  
  
##  <a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle  
 Вызовите эту функцию-член для получения расширенных стилей, используемых для `CComboBoxEx` элемента управления.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `DWORD` Значение, которое содержит расширенные стили, используемые для элемента управления полем со списком.  
  
### <a name="remarks"></a>Примечания  
 В разделе [ComboBoxEx управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb775742) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения об этих стилях.  
  
##  <a name="getimagelist"></a>CComboBoxEx::GetImageList  
 Вызовите эту функцию-член для получения указателя на список изображений, используемый `CComboBoxEx` элемента управления.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта. Если происходит сбой, эта функция-член возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 `CImageList` Объект, на который указывает возвращаемое значение является временным и уничтожается во время следующей обработки времени простоя.  
  
##  <a name="getitem"></a>CComboBoxEx::GetItem  
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
 Эта функция-член реализует функциональность сообщения [CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="haseditchanged"></a>CComboBoxEx::HasEditChanged  
 Определяет, если пользователь изменил содержимое **ComboBoxEx** редактирование элемента управления вводом.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данные, введенные пользователем в элемент управления поля ввода; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="insertitem"></a>CComboBoxEx::InsertItem  
 Вставляет новый элемент в **ComboBoxEx** управления.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pCBItem`  
 Указатель на [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) структуру, которая будет получать сведения об элементе. Эта структура содержит значения флага обратного вызова для элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс, в которую был вставлен новый элемент, если выполнено успешно; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 При вызове `InsertItem`, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений с [CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764) отправляется уведомление родительского окна.  
  
##  <a name="setextendedstyle"></a>CComboBoxEx::SetExtendedStyle  
 Вызовите эту функцию-член для задания расширенных стилей, используемых для расширенного управления списком.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExMask`  
 Объект `DWORD` значение, указывающее, какие стили в `dwExStyles` , могут быть затронуты. Расширенные стили в `dwExMask` будет изменен. Все другие стили будут сохранены как есть. Если этот параметр равен нулю, то все стили в `dwExStyles` снижается.  
  
 `dwExStyles`  
 A `DWORD` расширенные стили, чтобы задать для элемента управления значение, которое содержит поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `DWORD` значение, которое содержит расширенные стили, которые ранее использовались для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [ComboBoxEx управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb775742) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения об этих стилях.  
  
 Для создания расширенных windows расширенные стили элемента управления списком, используйте [CreateEx](#createex).  
  
##  <a name="setimagelist"></a>CComboBoxEx::SetImageList  
 Задает список изображений для **ComboBoxEx** управления.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий изображения для использования в `CComboBoxEx` элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, содержащий изображения, ранее используемые `CComboBoxEx` элемента управления. **NULL** Если список изображений не было установлено ранее.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует функциональность сообщения [CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Если изменить высоту элемента управления по умолчанию, вызовите функцию Win32 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) для изменения размеров элемента управления после вызова метода `SetImageList`, или он будет отображаться правильно.  
  
 `CImageList` Объект, на который указывает возвращаемое значение является временным и уничтожается во время следующей обработки времени простоя.  
  
##  <a name="setitem"></a>CComboBoxEx::SetItem  
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
 Эта функция-член реализует функциональность сообщения [CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setwindowtheme"></a>CComboBoxEx::SetWindowTheme  
 Задает поле визуальный стиль Расширенное поле со списком.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 `pszSubAppName`  
 Указатель на строку Юникода, содержит визуальный стиль поле Расширенное поле со списком для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCIE](../../visual-cpp-samples.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)

