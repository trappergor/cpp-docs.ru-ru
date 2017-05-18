---
title: "Класс CMFCToolBarComboBoxButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarComboBoxButton class
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
caps.latest.revision: 30
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
ms.openlocfilehash: 43369e8869f9dd58543016bd74547b24fbe183a5
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarcomboboxbutton-class"></a>Класс CMFCToolBarComboBoxButton
Кнопки панели инструментов, которая содержит поле со списком ( [CComboBox-класс](../../mfc/reference/ccombobox-class.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Создает документ `CMFCToolBarComboBoxButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](#additem)|Добавляет элемент в конец списка.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Добавляет элемент в списке. Порядок элементов в списке определяется `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|Сравнивает два элемента. Вызывается для сортировки элементов, `AddSortedItems` добавляет в раскрывающемся списке.|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Создает новый элемент управления для кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Удаляет элемент из списка.|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Возвращает индекс элемента, который содержит указанную строку.|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Возвращает указатель на кнопку поле со списком с идентификатором указанную команду.|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Возвращает указатель на элемент управления ComboBox, внедренный в кнопке поле со списком.|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Возвращает число элементов в поле со списком списке.|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Находит поле со списком поле кнопки, которая имеет идентификатор указанной команды. Возвращает число элементов в поле со списком списке этой кнопки.|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Возвращает индекс элемента, выбранного в поле со списком списке.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Находит поле кнопку, которая имеет идентификатор указанной команды и возвращает индекс элемента, выбранного в поле со списком списка поля, кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Возвращает указатель на элемент управления редактирования, внедренный в кнопке поле со списком.|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Возвращает строку, связанный с указанным индексом в поле со списком списке.|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Находит поле кнопку, которая имеет идентификатор указанной команды и возвращает строку, которая связана с индексом в списке поле со списком, кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Возвращает список 32-разрядное значение, который связан с указанным индексом в поле со списком.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Находит кнопке с заданным Идентификатором команды и возвращает 32-разрядное значение, связанный с индексом в списке поле со списком, кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Находит поле со списком поле кнопки, которая имеет идентификатор указанной команды. Получает 32-разрядное значение, которое является связанный индекс в списке поле со списком, кнопки и возвращает 32-разрядное значение как указатель.|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Возвращает текст из поля ввода, поля со списком.|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Находит поле кнопку, которая имеет идентификатор указанной команды и возвращает текст из элемента управления редактирования, кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Определяет, по центру или выровнен относительно верхней панели инструментов кнопки поля со списком в приложении.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Определяет, имеют ли кнопки поля со списком в приложении плоский внешний вид.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Удаляет все элементы из списка и измените элемент управления списком.|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Выбирает элемент в поле со списком в соответствии с его индекс, 32-разрядное значение или строка и уведомляет элемент управления поля со списком к выделенному фрагменту.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Находит поле со списком поле кнопки, которая имеет идентификатор указанной команды. Вызовы `SelectItem` выбрать элемент в поле со списком, кнопки в соответствии с его строки, индекса или 32-разрядное значение.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Указывает, по центру по вертикали или выровнен относительно верхней панели инструментов кнопки поля со списком в приложении.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Высота раскрывающегося списка.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Указывает, имеют ли кнопки поля со списком в приложении плоский вид.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы добавить кнопки поля со списком на панели инструментов, выполните следующие действия.  
  
 1. Зарезервируйте идентификатор фиктивный ресурс для кнопки в родительский ресурс панели инструментов.  
  
 2. Создать `CMFCToolBarComboBoxButton` объекта.  
  
 3. В обработчике сообщений, который обрабатывает `AFX_WM_RESETTOOLBAR` сообщений, заменить фиктивные кнопку новой кнопки поля со списком с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md). Пример кнопки поля со списком см. пример проекта VisualStudioDemo.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCToolBarComboBoxButton` класса. В примере показано включение поля редактирования и поля со списком, установите поле кнопки вертикальное положение поля со списком в приложении, задайте высоту окна списка при его удалении, задайте плоский внешний вид для кнопки поля со списком в приложении и задать текст в поле ввода, кнопки поля со списком. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#36;](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#37;](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarcomboboxbutton.h  
  
##  <a name="additem"></a>CMFCToolBarComboBoxButton::AddItem  
 Добавляет уникальный элемент списка.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszItem`  
 Текстовый элемент, добавляемый в список.  
  
 [in] `dwData`  
 Данные, связанные с элементом, чтобы добавить в список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс последнего элемента в списке.  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот метод при сортировке списка стилю поля.  
  
 Если текст элемента уже находится в списке, новые данные хранятся с существующим элементом. Поиск элемента с учетом регистра.  
  
##  <a name="addsorteditem"></a>CMFCToolBarComboBoxButton::AddSortedItem  
 Добавляет элемент в списке в порядке, в котором определяется [сравнения](#compare) метод.  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszItem`  
 Текстовый элемент, добавляемый в список.  
  
 [in] `dwData`  
 Данные, связанные с элементом, чтобы добавить в список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента, который был добавлен в список.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для добавления элементов в поле со списком в определенном порядке.  
  
##  <a name="canbestretched"></a>CMFCToolBarComboBoxButton::CanBeStretched  
 Указывает, можно ли изменить размер кнопки поля со списком.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE`.  
  
##  <a name="cmfctoolbarcomboboxbutton"></a>CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton  
 Создает [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) объекта.  
  
```  
CMFCToolBarComboBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=CBS_DROPDOWNLIST,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор команды «Создать».  
  
 [in] `iImage`  
 Индекс изображения, изображения, связанного с новой кнопки.  
  
 [in] `dwStyle`  
 Стиль новой кнопки.  
  
 [in] `iWidth`  
 Ширина в пикселях новой кнопки.  
  
### <a name="remarks"></a>Примечания  
 Ширина по умолчанию составляет 150 пикселей.  
  
 Список стилей кнопок панели инструментов в разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="cleardata"></a>CMFCToolBarComboBoxButton::ClearData  
 Удаление пользовательских данных.  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод в производном классе, если требуется удалить все определенные пользователем данные.  
  
##  <a name="compare"></a>CMFCToolBarComboBoxButton::Compare  
 Сравнивает две строки.  
  
```  
virtual int Compare(
    LPCTSTR lpszItem1,  
    LPCTSTR lpszItem2);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszItem1`  
 Первая сравниваемая строка.  
  
 [in] `lpszItem2`  
 Вторая сравниваемая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее, учитывается лексикографический связь между строками. В следующей таблице перечислены возможные значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|\<0|Первая строка меньше, чем второй.|  
|0|Первая строка равна второй.|  
|>0|Первая строка больше, чем второй.|  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы изменить способ сортировки элементов в поле со списком.  
  
 При сравнении учитывается регистр.  
  
 Этот метод вызывается только из [AddSortedItem](#addsorteditem) метод.  
  
##  <a name="copyfrom"></a>CMFCToolBarComboBoxButton::CopyFrom  
 Копирует состояние указанного `CMFCToolBarComboBoxButton` на текущий объект.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Исходный объект `CMFCToolBarComboBoxButton`.  
  
##  <a name="createcombo"></a>CMFCToolBarComboBoxButton::CreateCombo  
 Создает новый поле со списком, кнопки поля со списком.  
  
```  
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на родительское окно кнопки.  
  
 [in] `rect`  
 Ограничивающий прямоугольник поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый поле со списком, если метод был выполнен успешно; в противном случае — `NULL`.  
  
##  <a name="createedit"></a>CMFCToolBarComboBoxButton::CreateEdit  
 Создает новые поля ввода, кнопки поля со списком.  
  
```  
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на родительское окно кнопки.  
  
 [in] `rect`  
 Поле ввода нового ограничивающего прямоугольника.  
  
 [in] `dwEditStyle`  
 Стиль элемента управления нового поля ввода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новые поля ввода, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при создании нового поля ввода, кнопки поля со списком. Переопределите этот метод, чтобы изменить способ [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) создается.  
  
##  <a name="deleteitem"></a>CMFCToolBarComboBoxButton::DeleteItem  
 Удаляет указанный элемент из списка.  
  
```  
BOOL DeleteItem(int iIndex);  
BOOL DeleteItem(DWORD_PTR dwData);  
  BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс удаляемого элемента.  
  
 [in] `dwData`  
 Данные, связанные с удаляемого элемента.  
  
 [in] `lpszText`  
 Текст удаляемого элемента. При наличии нескольких элементов с одинаковым текстом, удаляется первый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент был находятся и успешно удален; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="duplicatedata"></a>CMFCToolBarComboBoxButton::DuplicateData  
 Дубликаты пользовательских данных.  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод в производном классе, если требуется скопировать любые данные, определенные пользователем.  
  
##  <a name="enablewindow"></a>CMFCToolBarComboBoxButton::EnableWindow  
 Включает или отключает поля редактирования и поля со списком.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить поля редактирования и поля со списком; `FALSE` отключение поля редактирования и поля со списком.  
  
### <a name="remarks"></a>Примечания  
 При отключении элементов управления не может стать активным и не может принимать входные данные пользователя.  
  
##  <a name="exporttomenubutton"></a>CMFCToolBarComboBoxButton::ExportToMenuButton  
 Копирует строки из таблицы строки приложение указанного меню, с помощью команды кнопки поле со списком идентификатор.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `menuButton`  
 Ссылка на меню кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE`.  
  
##  <a name="finditem"></a>CMFCToolBarComboBoxButton::FindItem  
 Возвращает индекс первого элемента в поле со списком, который содержит указанную строку.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszText`  
 Текст, который требуется найти в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента; или `CB_ERR` , если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getbycmd"></a>CMFCToolBarComboBoxButton::GetByCmd  
 Возвращает указатель на кнопки поля со списком, которая имеет идентификатор указанной команды.  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поля со списком.  
  
 [in] `bIsFocus`  
 `TRUE`для поиска только с фокусом ввода кнопок; `FALSE` для поиска всех кнопок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на экземпляр кнопки поля со списком. или `NULL` Если кнопка не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcombobox"></a>CMFCToolBarComboBoxButton::GetComboBox  
 Возвращает указатель на поле со списком в поле со списком кнопке.  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CComboBox-класс](../../mfc/reference/ccombobox-class.md) объекта, если метод был успешным; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcontextmenuid"></a>CMFCToolBarComboBoxButton::GetContextMenuID  
 Возвращает идентификатор ресурса контекстное меню для кнопки поля со списком.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Контекстное меню для идентификатора ресурса.  
  
##  <a name="getcount"></a>CMFCToolBarComboBoxButton::GetCount  
 Возвращает количество элементов в списке.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcountall"></a>CMFCToolBarComboBoxButton::GetCountAll  
 Возвращает количество элементов в поле со списком, кнопки поля со списком, имеет идентификатор указанной команды.  
  
```  
static int GetCountAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в поле со списком; в противном случае — `CB_ERR` Если кнопки поля со списком не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcursel"></a>CMFCToolBarComboBoxButton::GetCurSel  
 Возвращает индекс текущего выделенного элемента в поле со списком.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс текущего выделенного элемента в поле со списком; или `CB_ERR` , если элемент не выбран.  
  
### <a name="remarks"></a>Примечания  
 Поле списка индекс начинается с нуля.  
  
##  <a name="getcurselall"></a>CMFCToolBarComboBoxButton::GetCurSelAll  
 Возвращает индекс текущего выделенного элемента в поле со списком списком поле кнопки, которая имеет идентификатор указанной команды.  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс текущего выделенного элемента в поле со списком; в противном случае — `CB_ERR` , если элемент не выбран или не найден кнопки поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Поле списка индекс начинается с нуля.  
  
##  <a name="geteditctrl"></a>CMFCToolBarComboBoxButton::GetEditCtrl  
 Возвращает указатель на поле ввода в поле со списком кнопке.  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на поле ввода, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethwnd"></a>CMFCToolBarComboBoxButton::GetHwnd  
 Возвращает дескриптор окна для поля со списком.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна или `NULL` Если поле со списком не связан с объектом окна.  
  
##  <a name="getitem"></a>CMFCToolBarComboBoxButton::GetItem  
 Возвращает строку, связанную с элементом с заданным индексом в списке.  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, связанную с элементом; в противном случае — `NULL` недопустимый параметр индекса или если параметр индекса равен -1 и отсутствует элемент, выбранный в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Индексный параметр-1 возвращает строку элемента, который выбран в данный момент.  
  
##  <a name="getitemall"></a>CMFCToolBarComboBoxButton::GetItemAll  
 Возвращает строку, связанную с элементом с заданным индексом в поле со списком, кнопки поля со списком, имеет идентификатор указанной команды.  
  
```  
static LPCTSTR GetItemAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поля со списком.  
  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку элемента, если метод был выполнен успешно; в противном случае — `NULL` Если индекс является недопустимым, кнопки поля со списком не найден, или если индекс равен -1 и отсутствует элемент, выбранный в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Значение индекса-1 возвращает строку элемента, который выбран в данный момент.  
  
##  <a name="getitemdata"></a>CMFCToolBarComboBoxButton::GetItemData  
 Возвращает данные, связанные с элементом в списке с указанным индексом.  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные, связанные с элементом; или 0, если элемент не существует.  
  
### <a name="remarks"></a>Примечания  
 Индексный параметр-1 возвращает данные, связанные с текущего выделенного элемента.  
  
##  <a name="getitemdataall"></a>CMFCToolBarComboBoxButton::GetItemDataAll  
 Возвращает данные, связанные с элементом с указанным индексом в поле со списком, кнопки поля со списком, имеет идентификатор конкретной команды.  
  
```  
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поля со списком.  
  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные, связанные с элементом, если метод был выполнен успешно; в противном случае — 0, если указанный индекс является недопустимым или не найден CB_ERR, если кнопка с полем со списком.  
  
### <a name="remarks"></a>Примечания  
 Индексный параметр-1 возвращает данные, связанные с текущего выделенного элемента.  
  
##  <a name="getitemdataptrall"></a>CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 Возвращает данные, связанные с элементом с указанным индексом в поле со списком, кнопки поля со списком, имеет идентификатор конкретной команды. Эти данные возвращаются как указатель.  
  
```  
static void* GetItemDataPtrAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поля со списком.  
  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель, связанный с элементом, если метод был выполнен успешно; в противном случае — значение -1, если возникает ошибка, или `NULL` Если кнопки поля со списком не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getprompt"></a>CMFCToolBarComboBoxButton::GetPrompt  
 Возвращает строку приглашения для поля со списком кнопке.  
  
```  
virtual CString GetPrompt() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка приглашения.  
  
### <a name="remarks"></a>Примечания  
 В настоящее время этот метод не реализован.  
  
##  <a name="gettext"></a>CMFCToolBarComboBoxButton::GetText  
 Возвращает текст в поле ввода.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст в поле ввода.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettextall"></a>CMFCToolBarComboBoxButton::GetTextAll  
 Возвращает текст в поле ввода, кнопки поля со списком, имеет идентификатор указанной команды.  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поле указанные поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст в поле редактирования, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasfocus"></a>CMFCToolBarComboBoxButton::HasFocus  
 Указывает, является ли поле со списком в данный момент имеет фокус.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если поле со списком в данный момент имеет фокус; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод также возвращает `TRUE` Если любого дочернего окна со списком в данный момент имеет фокус.  
  
##  <a name="iscentervert"></a>CMFCToolBarComboBoxButton::IsCenterVert  
 Возвращает вертикальное положение кнопки поля со списком в приложении.  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопки по центру; `FALSE` Если кнопки располагаются сверху.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isflatmode"></a>CMFCToolBarComboBoxButton::IsFlatMode  
 Возвращает плоский внешний вид для кнопки поля со списком в приложении.  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопки имеют плоский; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию используется плоский стиль для кнопки поля со списком`FALSE.`  
  
##  <a name="isownerof"></a>CMFCToolBarComboBoxButton::IsOwnerOf  
 Указывает, связан ли указанный дескриптор с кнопки поля со списком или один из его дочерних элементов.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hwnd`  
 Дескриптор окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если дескриптор assocated кнопки поля со списком или его дочерними элементами. в противном случае — `FALSE`.  
  
##  <a name="isribbonbutton"></a>CMFCToolBarComboBoxButton::IsRibbonButton  
 Указывает, находится ли кнопка поле со списком на панели ленты.  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `FALSE`, что означает поле со списком кнопке никогда не отображается на панели ленты.  
  
##  <a name="iswindowvisible"></a>CMFCToolBarComboBoxButton::IsWindowVisible  
 Возвращает состояние видимости для поля со списком кнопке.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние видимости кнопки поля со списком.  
  
##  <a name="notifycommand"></a>CMFCToolBarComboBoxButton::NotifyCommand  
 Указывает, обрабатывает ли кнопки со списком сообщения.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iNotifyCode`  
 Сообщение уведомления, связанный с командой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Является ли кнопки со списком обрабатывает сообщение.  
  
##  <a name="onaddtocustomizepage"></a>CMFCToolBarComboBoxButton::OnAddToCustomizePage  
 Вызывается инфраструктурой при добавлении кнопки **Настройка** диалоговое окно.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
##  <a name="oncalculatesize"></a>CMFCToolBarComboBoxButton::OnCalculateSize  
 Вызывается платформой для вычисления размера кнопки.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, отображается кнопка поле со списком.  
  
 [in] `sizeDefault`  
 Размер по умолчанию, кнопки поля со списком.  
  
 [in] `bHorz`  
 Состояние закрепления панели инструментов родительской. `TRUE`Если панель закреплена горизонтально и `FALSE` при вертикально закрепленной панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `SIZE` структуру, содержащую измерения кнопки поля со списком в пикселях.  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarComboBoxButton::OnChangeParentWnd  
 Вызывается инфраструктурой при вставке в новой панели инструментов кнопку поле со списком.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на новую панель инструментов родительского.  
  
##  <a name="onclick"></a>CMFCToolBarComboBoxButton::OnClick  
 Вызывается инфраструктурой при нажатии пользователем кнопки поля со списком.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на родительское окно кнопки поля со списком.  
  
 [in] `bDelay`  
 Зарезервировано для использования в производном классе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод обрабатывает событие; в противном случае — `FALSE`.  
  
##  <a name="onctlcolor"></a>CMFCToolBarComboBoxButton::OnCtlColor  
 Вызывается платформой, когда пользователь изменяет цвет инструментов родительского, задайте цвет кнопки поля со списком.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, отображается кнопка поле со списком.  
  
 [in] `nCtlColor`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор кисть, она используется для рисования фона кнопки, поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Этот метод также задает цвет текста кнопки поля со списком.  
  
##  <a name="ondraw"></a>CMFCToolBarComboBoxButton::OnDraw  
 Вызывается платформой для отображения кнопки поля со списком с помощью указанного стили и параметры.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Pdc`  
 Контекст устройства, который отображает кнопки.  
  
 [in] `rect`  
 Ограничивающий прямоугольник кнопки.  
  
 [in] `pImages`  
 Коллекция изображений, связанного с кнопкой.  
  
 [in] `bHorz`  
 Состояние закрепления панели инструментов родительской. `TRUE`Если панель закреплена горизонтально и `FALSE` при вертикально закрепленной панели инструментов.  
  
 [in] `bCustomizeMode`  
 Ли оно в режим настройки.  
  
 [in] `bHighlight`  
 Следует ли Рисование выделенной кнопкой поле со списком.  
  
 [in] `bDrawBorder`  
 Необходимость отображения кнопки поля со списком с границей.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE`Чтобы нарисовать затененный отключенных кнопок; `FALSE` отключено использование изображений в коллекции.  
  
##  <a name="ondrawoncustomizelist"></a>CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 Вызывается платформой для отображения кнопки поля со списком в **команды** области **Настройка** диалоговое окно.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, отображается кнопка поле со списком.  
  
 [in] `rect`  
 Ограничивающий прямоугольник кнопки поля со списком.  
  
 [in] `bSelected`  
 `TRUE`Если кнопка с полем со списком выбран; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина в пикселях, кнопки поля со списком.  
  
##  <a name="onglobalfontschanged"></a>CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 Вызывается средой, чтобы задать поле со списком Шрифт кнопку поле, при изменении шрифта приложения.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="onmove"></a>CMFCToolBarComboBoxButton::OnMove  
 Вызывается платформой для изменения расположения кнопки поля со списком при перемещении родительского инструментов.  
  
```  
virtual void OnMove();
```  
  
##  <a name="onshow"></a>CMFCToolBarComboBoxButton::OnShow  
 Вызывается инфраструктурой при скрыто или отображается кнопка поле со списком.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 Нужно ли скрыть или отобразить кнопку поле со списком.  
  
##  <a name="onsize"></a>CMFCToolBarComboBoxButton::OnSize  
 Вызывается средой, чтобы изменить размер кнопки, поля со списком изменении размера панели инструментов родительской.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iSize`  
 Новая ширина кнопки поля со списком.  
  
##  <a name="onupdatetooltip"></a>CMFCToolBarComboBoxButton::OnUpdateToolTip  
 Вызывается платформой, когда пользователь изменяет всплывающая подсказка для кнопки поля со списком.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на родительское окно кнопки поля со списком.  
  
 [in] `iButtonIndex`  
 Идентификатор кнопки поля со списком.  
  
 [in] `wndToolTip`  
 Всплывающая подсказка для связи с помощью кнопки поля со списком.  
  
 [in] `str`  
 Текст подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод обрабатывает событие; в противном случае — `FALSE`.  
  
##  <a name="removeallitems"></a>CMFCToolBarComboBoxButton::RemoveAllItems  
 Удаляет все элементы из списка и изменить поля.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет все элементы из списка и измените элемент управления списком.  
  
##  <a name="selectitem"></a>CMFCToolBarComboBoxButton::SelectItem  
 Выбирает элемент в списке.  
  
```  
BOOL SelectItem(
    int iIndex,  
    BOOL bNotify=TRUE);  
  
BOOL SelectItem(DWORD_PTR dwData);  
BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
 [in] `bNotify`  
 `TRUE`Чтобы уведомить кнопки поля со списком выбора; в противном случае `FALSE`.  
  
 [in] `dwData`  
 Данные, связанные с элементом в списке.  
  
 [in] `lpszText`  
 Текст элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="selectitemall"></a>CMFCToolBarComboBoxButton::SelectItemAll  
 Выбирает элемент в поле со списком, кнопки поля со списком, имеет идентификатор указанной команды.  
  
```  
static BOOL SelectItemAll(
    UINT uiCmd,  
    int iIndex);

 
static BOOL SelectItemAll(
    UINT uiCmd,  
    DWORD_PTR dwData);

 
static BOOL SelectItemAll(
    UINT uiCmd,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки поля со списком, который содержит поле со списком.  
  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке. Значение -1, снимает текущее выделение в поле со списком и очищает поля ввода.  
  
 [in] `dwData`  
 Данные элемента в списке.  
  
 [in] `lpszText`  
 Текст элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="serialize"></a>CMFCToolBarComboBoxButton::Serialize  
 Считывает этот объект из архива и записывает его в архив.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `ar`  
 `CArchive` Объект для сериализации.  
  
### <a name="remarks"></a>Примечания  
 Параметры в `CArchive` объекта определить, является ли этот метод считывает или записывает в архив.  
  
##  <a name="setaccdata"></a>CMFCToolBarComboBoxButton::SetACCData  
 Заполняет указанный `CAccessibilityData` объекта с помощью специальных данных с помощью кнопки поля со списком.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
 Родительское окно кнопки поля со списком.  
  
 [выходной] `data`  
 Объект `CAccessibilityData` объект, получающий данные специальных возможностей с помощью кнопки поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
##  <a name="setcentervert"></a>CMFCToolBarComboBoxButton::SetCenterVert  
 Задает вертикальное положение кнопки поля со списком в приложении.  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCenterVert`  
 `TRUE`центр кнопки поля со списком на панели инструментов; `FALSE` выравнивание кнопки поля со списком в верхней части панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию кнопки поля со списком выравниваются в начало.  
  
##  <a name="setcontextmenuid"></a>CMFCToolBarComboBoxButton::SetContextMenuID  
 Задает идентификатор ресурса контекстное меню для поля со списком кнопке.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiResID`  
 Контекстное меню для идентификатора ресурса.  
  
##  <a name="setdropdownheight"></a>CMFCToolBarComboBoxButton::SetDropDownHeight  
 Задает высоту окна списка, при перетаскивании.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHeight`  
 Высота в пикселях списка.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию высота — 150 пикселей.  
  
##  <a name="setflatmode"></a>CMFCToolBarComboBoxButton::SetFlatMode  
 Задает плоский внешний вид для кнопки поля со списком в приложении.  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bFlat`  
 `TRUE`для плоский внешний вид; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию используется плоский стиль для кнопки поля со списком `FALSE`.  
  
##  <a name="setstyle"></a>CMFCToolBarComboBoxButton::SetStyle  
 Задает указанный стиль для поля со списком кнопке и обновит элемент управления, если она не отключена.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nStyle`  
 Побитовое сочетание (или) стилей на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Список стилей кнопок панели инструментов в разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="settext"></a>CMFCToolBarComboBoxButton::SetText  
 Задает текст в поле ввода поля со списком кнопке.  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszText`  
 Указатель на строку, которая содержит текст для поля ввода.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Пошаговое руководство: Добавление элементов управления в панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)




