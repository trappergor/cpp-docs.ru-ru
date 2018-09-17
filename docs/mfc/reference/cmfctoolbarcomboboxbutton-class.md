---
title: Класс CMFCToolBarComboBoxButton | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffb17f8f38e83399ec32b792338f818cc06215dc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703785"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>Класс CMFCToolBarComboBoxButton
Кнопки панели инструментов, содержащий поле со списком ( [класс CComboBox](../../mfc/reference/ccombobox-class.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Создает документ `CMFCToolBarComboBoxButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](#additem)|Добавляет элемент в конец списка.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Добавляет элемент в поле со списком. Порядок элементов в списке определяется `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|Сравнивает два элемента. Вызывается для сортировки элементов, которое `AddSortedItems` добавляет поле со списком.|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Создает новый элемент управления для кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Удаляет элемент из списка.|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Возвращает индекс элемента, который содержит указанную строку.|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Возвращает указатель на кнопку в окне со списком с указанным идентификатором команды.|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Возвращает указатель на поле со списком, внедренного в кнопке поле со списком.|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Возвращает число элементов в поле со списком, окне со списком.|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Находит поле со списком кнопку в окне с указанным идентификатором команды. Возвращает число элементов в поле со списком списка этой кнопки.|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Возвращает индекс выбранного элемента в поле со списком, окне со списком.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Находит окно кнопку, которая имеет заданный идентификатор команды и возвращает индекс элемента, выбранного в поле со списком Список этой кнопки в поле со списком.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Возвращает указатель на элемент управления редактирования, который внедряется в поле со списком кнопки.|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Возвращает строку, связанный с указанным индексом в поле со списком, окне со списком.|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Находит поле кнопка, которая имеет заданный идентификатор команды и возвращает строку, которая связана с индексом, в поле со списком, кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Возвращает 32-разрядное значение, который связан с указанным индексом в поле со списком, окне со списком.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Находит окно кнопку, которая имеет заданный идентификатор команды и возвращает 32-разрядное значение, которая связана с индексом, в поле со списком, кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Находит поле со списком кнопку в окне с указанным идентификатором команды. Извлекает 32-разрядное значение, которое является связанный индекс в поле со списком, кнопки и возвращает 32-разрядное значение как указатель.|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Возвращает текст из поля ввода в поле со списком.|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Находит окно кнопку, которая имеет заданный идентификатор команды и возвращает текст из элемента управления редактирования этой кнопки поля со списком.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Определяет, по центру или по краю по верхнему краю панели инструментов кнопки поля со списком в приложении.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Определяет, имеют ли кнопки поля со списком в приложении плоский внешний вид.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Удаляет все элементы из списка, поле и элемент управления поля со списком.|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Выбирает элемент в поле со списком в соответствии с его индекс, 32-разрядное значение или строка и уведомляет поле со списком к выделенному фрагменту.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Находит поле со списком кнопку в окне с указанным идентификатором команды. Вызовы `SelectItem` выбрать элемент в поле со списком, кнопки в соответствии с его строка, индекс или 32-разрядное значение.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Определяет, по центру по вертикали или выравниваются по верхнему краю панели инструментов кнопки поля со списком в приложении.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Задает высоту поля с раскрывающимся списком.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Указывает, имеют ли кнопки поля со списком в приложении плоский внешний вид.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы добавить кнопку поле со списком на панели инструментов, выполните следующие действия:  
  
 1. Зарезервируйте идентификатор фиктивный ресурс для кнопки в панели инструментов к родительскому ресурсу.  
  
 2. Создать `CMFCToolBarComboBoxButton` объекта.  
  
 3. В обработчике сообщений, который обрабатывает сообщение AFX_WM_RESETTOOLBAR, заменить фиктивные кнопку "Создать поле" поле со списком с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md). Пример кнопки панели инструментов поле со списком см. пример проекта VisualStudioDemo.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCToolBarComboBoxButton` класса. В примере для включения поля редактирования и поля со списком, задайте поле кнопок вертикальное положение поля со списком в приложении, установите высоту окна списка, при его вставке, задайте плоский внешний вид кнопок поле со списком в приложении , а затем установите текст в поле ввода поля со списком кнопку в окне. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarcomboboxbutton.h  
  
##  <a name="additem"></a>  CMFCToolBarComboBoxButton::AddItem  
 Добавляет уникальный элемент в поле со списком.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Параметры  
*lpszItem*<br/>
[in] Текст для элемента, который необходимо добавить в список.  
  
*dwData*<br/>
[in] Данные, связанные с элементом, чтобы добавить в список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс последнего элемента в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот метод, при сортировке стилю поля списка.  
  
 Если текст элемента уже находится в поле со списком, новые данные хранятся с существующего элемента. Поиск нужного элемента чувствительно к регистру.  
  
##  <a name="addsorteditem"></a>  CMFCToolBarComboBoxButton::AddSortedItem  
 Добавляет элемент в списке в порядке, в котором определяется [сравнения](#compare) метод.  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Параметры  
*lpszItem*<br/>
[in] Текст для элемента, который необходимо добавить в список.  
  
*dwData*<br/>
[in] Данные, связанные с элементом, чтобы добавить в список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента, который был добавлен в список.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для добавления элементов в поле со списком в определенном порядке.  
  
##  <a name="canbestretched"></a>  CMFCToolBarComboBoxButton::CanBeStretched  
 Указывает, можно ли изменить размер кнопки поля со списком.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE.  
  
##  <a name="cmfctoolbarcomboboxbutton"></a>  CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton  
 Создает [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) объекта.  
  
```  
CMFCToolBarComboBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=CBS_DROPDOWNLIST,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Параметры  
*uiID*<br/>
[in] Идентификатор команды "Создать".  
  
*iImage*<br/>
[in] Индекс изображения, изображения, связанного с новой кнопки.  
  
*dwStyle*<br/>
[in] Стиль "Создать".  
  
*iWidth*<br/>
[in] Ширина в пикселях "Создать".  
  
### <a name="remarks"></a>Примечания  
 Ширина по умолчанию — 150 пикселей.  
  
 Список стили кнопок панели инструментов см. в разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="cleardata"></a>  CMFCToolBarComboBoxButton::ClearData  
 Удаляет пользовательские данные.  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод в производном классе, если вы хотите удалить все пользовательские данные.  
  
##  <a name="compare"></a>  CMFCToolBarComboBoxButton::Compare  
 Сравнивает две строки.  
  
```  
virtual int Compare(
    LPCTSTR lpszItem1,  
    LPCTSTR lpszItem2);
```  
  
### <a name="parameters"></a>Параметры  
*lpszItem1*<br/>
[in] Первая сравниваемая строка.  
  
*lpszItem2*<br/>
[in] Вторая сравниваемая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее, с учетом регистра лексикографическим связь между строками. В следующей таблице перечислены возможные значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|\<0|Первая строка меньше, чем второй.|  
|0|Первая строка равна второй.|  
|>0|Первая строка больше, чем второй.|  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы изменить способ сортировки элементов в поле со списком.  
  
 При сравнении учитывается регистр.  
  
 Этот метод вызывается только из [AddSortedItem](#addsorteditem) метод.  
  
##  <a name="copyfrom"></a>  CMFCToolBarComboBoxButton::CopyFrom  
 Копирует состояние указанного `CMFCToolBarComboBoxButton` текущему объекту.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
*src*<br/>
[in] Источник `CMFCToolBarComboBoxButton` объекта.  
  
##  <a name="createcombo"></a>  CMFCToolBarComboBoxButton::CreateCombo  
 Создает новое окно со списком для кнопки поля со списком.  
  
```  
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
*pWndParent*<br/>
[in] Указатель на родительское окно кнопки.  
  
*Rect*<br/>
[in] Ограничивающий прямоугольник в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый поле со списком, если метод был выполнен успешно; в противном случае — значение NULL.  
  
##  <a name="createedit"></a>  CMFCToolBarComboBoxButton::CreateEdit  
 Создает новое окно редактирования для кнопки поля со списком.  
  
```  
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Параметры  
*pWndParent*<br/>
[in] Указатель на родительское окно кнопки.  
  
*Rect*<br/>
[in] Ограничивающий прямоугольник для нового поля ввода.  
  
*dwEditStyle*<br/>
[in] Стиль элемента управления нового поля редактирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новое поле ввода, если метод был выполнен успешно; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при создании нового поля ввода для кнопки поля со списком. Переопределите этот метод, чтобы изменить способ [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) создается.  
  
##  <a name="deleteitem"></a>  CMFCToolBarComboBoxButton::DeleteItem  
 Удаляет указанный элемент из списка.  
  
```  
BOOL DeleteItem(int iIndex);  
BOOL DeleteItem(DWORD_PTR dwData);  
  BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс удаляемого элемента.  
  
*dwData*<br/>
[in] Данные, связанные с элементом для удаления.  
  
*lpszText*<br/>
[in] Текст элемента для удаления. При наличии нескольких элементов с одинаковым текстом, удаляется первый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент была размещена, а затем успешно удален; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="duplicatedata"></a>  CMFCToolBarComboBoxButton::DuplicateData  
 Повторяющиеся значения пользовательских данных.  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод в производном классе, если вы хотите скопировать все определенные пользователем данные.  
  
##  <a name="enablewindow"></a>  CMFCToolBarComboBoxButton::EnableWindow  
 Включает или отключает поля редактирования и поля со списком.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*bEnable*<br/>
[in] Значение TRUE, чтобы включить поля редактирования и поля со списком; Значение FALSE, чтобы отключить поля редактирования и поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Если элементы управления не станет активным, не может принимать ввод данных пользователем.  
  
##  <a name="exporttomenubutton"></a>  CMFCToolBarComboBoxButton::ExportToMenuButton  
 Копирует строку из таблицы строки приложения на заданное меню с помощью команды кнопки поля со списком ID.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
*MenuButton*<br/>
[out] Ссылка на кнопки меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение TRUE.  
  
##  <a name="finditem"></a>  CMFCToolBarComboBoxButton::FindItem  
 Возвращает индекс первого элемента в списке, который содержит указанную строку.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Параметры  
*lpszText*<br/>
[in] Текст, который требуется найти в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента; или CB_ERR, если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getbycmd"></a>  CMFCToolBarComboBoxButton::GetByCmd  
 Возвращает указатель на кнопку поле со списком, с указанным идентификатором команды.  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmd*<br/>
[in] Идентификатор команды, кнопки поля со списком.  
  
*bIsFocus*<br/>
[in] Значение true, чтобы только поиска с фокусом ввода кнопок; Значение FALSE, чтобы найти все кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на кнопку в окне со списком; или значение NULL, если кнопка не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcombobox"></a>  CMFCToolBarComboBoxButton::GetComboBox  
 Возвращает указатель на поле со списком в поле со списком кнопку в окне.  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [класс CComboBox](../../mfc/reference/ccombobox-class.md) объекта, если метод был выполнен успешно; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarComboBoxButton::GetContextMenuID  
 Получает идентификатор ресурса контекстное меню для кнопки поля со списком.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор контекстного меню ресурса.  
  
##  <a name="getcount"></a>  CMFCToolBarComboBoxButton::GetCount  
 Возвращает число элементов в поле со списком.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в поле со списком.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcountall"></a>  CMFCToolBarComboBoxButton::GetCountAll  
 Возвращает количество элементов в списке кнопки поля со списком с указанным идентификатором команды.  
  
```  
static int GetCountAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmd*<br/>
[in] Идентификатор команды, кнопки поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке; в противном случае CB_ERR, если кнопка поле со списком не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcursel"></a>  CMFCToolBarComboBoxButton::GetCurSel  
 Получает индекс выбранного элемента в поле со списком.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс выбранного элемента в списке; или CB_ERR, если элемент не выбран.  
  
### <a name="remarks"></a>Примечания  
 Отсчитываемый от нуля индекса поля со списком.  
  
##  <a name="getcurselall"></a>  CMFCToolBarComboBoxButton::GetCurSelAll  
 Возвращает индекс выбранного элемента в списке поле со списком кнопку в окне с указанным идентификатором команды.  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmd*<br/>
[in] Идентификатор команды, кнопки поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс выбранного элемента в списке; в противном случае — не найден CB_ERR, если элемент не выбран или кнопки поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Отсчитываемый от нуля индекса поля со списком.  
  
##  <a name="geteditctrl"></a>  CMFCToolBarComboBoxButton::GetEditCtrl  
 Возвращает указатель на поле ввода в поле со списком кнопку в окне.  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на поле ввода, если метод был выполнен успешно; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethwnd"></a>  CMFCToolBarComboBoxButton::GetHwnd  
 Возвращает дескриптор окна для поля со списком.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна, или значение NULL, если поле со списком не связан с объектом окна.  
  
##  <a name="getitem"></a>  CMFCToolBarComboBoxButton::GetItem  
 Возвращает строку, связанную с элементом с указанным индексом в списке.  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Параметры  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, которая связана с элементом; в противном случае — значение NULL, если параметр индекса недопустим, или параметр индекса равно -1, и отсутствует элемент, выбранный в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Параметр индекса-1 возвращает строку элемента, выбранное в настоящий момент.  
  
##  <a name="getitemall"></a>  CMFCToolBarComboBoxButton::GetItemAll  
 Возвращает строку, связанную с элементом с указанным индексом в списке кнопки поля со списком с указанным идентификатором команды.  
  
```  
static LPCTSTR GetItemAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmd*<br/>
[in] Идентификатор команды, кнопки поля со списком.  
  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку элемента, если метод был выполнен успешно; в противном случае — значение NULL, если индекс является недопустимым, кнопки поля со списком не найден, или если индекс равен -1, и отсутствует элемент, выбранный в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Значение индекса-1 возвращает строку элемента, выбранное в настоящий момент.  
  
##  <a name="getitemdata"></a>  CMFCToolBarComboBoxButton::GetItemData  
 Возвращает данные, связанные с элемента с указанным индексом в списке.  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Параметры  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные, связанные с элементом; или 0, если элемент не существует.  
  
### <a name="remarks"></a>Примечания  
 Параметр индекса-1 возвращает данные, связанные с текущего выбранного элемента.  
  
##  <a name="getitemdataall"></a>  CMFCToolBarComboBoxButton::GetItemDataAll  
 Возвращает данные, связанные с элементом с указанным индексом в списке кнопки поля со списком, имеет идентификатор определенной команде.  
  
```  
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmd*<br/>
[in] Идентификатор команды, кнопки поля со списком.  
  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные, связанные с элементом, если метод был выполнен успешно; в противном случае — 0, если указанный индекс не является допустимым или не найден CB_ERR, если кнопка поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Параметр индекса-1 возвращает данные, связанные с текущего выбранного элемента.  
  
##  <a name="getitemdataptrall"></a>  CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 Возвращает данные, связанные с элементом с указанным индексом в списке кнопки поля со списком, имеет идентификатор определенной команде. Эти данные возвращаются как указатель.  
  
```  
static void* GetItemDataPtrAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmd*<br/>
[in] Идентификатор команды, кнопки поля со списком.  
  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель, связанный с элементом, если метод был выполнен успешно; в противном случае — значение-1, когда возникает ошибка, или значение NULL, если кнопка поле со списком не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getprompt"></a>  CMFCToolBarComboBoxButton::GetPrompt  
 Возвращает строку подсказки для поля со списком кнопку в окне.  
  
```  
virtual CString GetPrompt() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка приглашения.  
  
### <a name="remarks"></a>Примечания  
 В настоящее время этот метод не реализуется.  
  
##  <a name="gettext"></a>  CMFCToolBarComboBoxButton::GetText  
 Получает текст в поле ввода.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст в поле ввода.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettextall"></a>  CMFCToolBarComboBoxButton::GetTextAll  
 Получает текст в поле ввода, кнопки поля со списком с указанным идентификатором команды.  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmd*<br/>
[in] Идентификатор команды кнопки поле указанные поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текст в поле ввода, если метод был выполнен успешно; в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasfocus"></a>  CMFCToolBarComboBoxButton::HasFocus  
 Указывает, является ли поле со списком в данный момент имеет фокус.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если поле со списком в данный момент имеет фокус; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод также возвращает значение TRUE, если любого дочернего окна, в поле со списком в данный момент имеет фокус.  
  
##  <a name="iscentervert"></a>  CMFCToolBarComboBoxButton::IsCenterVert  
 Возвращает вертикальное положение кнопки поля со списком в приложении.  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопки выравниваются по центру; Значение FALSE, если кнопки располагаются сверху.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isflatmode"></a>  CMFCToolBarComboBoxButton::IsFlatMode  
 Возвращает плоский внешний вид кнопок поле со списком в приложении.  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопки имеют плоский; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Плоский стиль по умолчанию для кнопок поле со списком имеет значение FALSE.  
  
##  <a name="isownerof"></a>  CMFCToolBarComboBoxButton::IsOwnerOf  
 Указывает, связан ли указанный дескриптор с кнопки поля со списком или один из его дочерних элементов.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>Параметры  
*HWND*<br/>
[in] Дескриптор окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если дескриптор, связанные с кнопки поля со списком или один из его дочерних элементов; в противном случае — значение FALSE.  
  
##  <a name="isribbonbutton"></a>  CMFCToolBarComboBoxButton::IsRibbonButton  
 Указывает, находится ли кнопка поле со списком на панели ленты.  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда имеет значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает значение FALSE, что означает, что кнопка поле со списком никогда не отображается на панели ленты.  
  
##  <a name="iswindowvisible"></a>  CMFCToolBarComboBoxButton::IsWindowVisible  
 Возвращает режим отображения поля со списком кнопку в окне.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние видимости кнопки поля со списком.  
  
##  <a name="notifycommand"></a>  CMFCToolBarComboBoxButton::NotifyCommand  
 Указывает, обрабатывает ли кнопки поля со списком сообщение.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Параметры  
*iNotifyCode*<br/>
[in] Сообщение уведомления, который связан с командой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поле ли поле со списком кнопка обрабатывает сообщение.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarComboBoxButton::OnAddToCustomizePage  
 Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
##  <a name="oncalculatesize"></a>  CMFCToolBarComboBoxButton::OnCalculateSize  
 Вызывается платформой для вычисления размера кнопки.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Контекст устройства, отображается кнопка поле со списком.  
  
*sizeDefault*<br/>
[in] Размер по умолчанию, кнопки поля со списком.  
  
*bHorz*<br/>
[in] Состояние закрепления панели инструментов родительского. Значение TRUE, если закрепления панели инструментов по горизонтали и FALSE при вертикально закрепления панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `SIZE` структура, содержащая размеры кнопки поля со списком в пикселях.  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarComboBoxButton::OnChangeParentWnd  
 Вызывается платформой при вставке в новой панели инструментов кнопку поле со списком.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
*pWndParent*<br/>
[in] Указатель на новую панель инструментов родительского.  
  
##  <a name="onclick"></a>  CMFCToolBarComboBoxButton::OnClick  
 Вызывается платформой, когда пользователь нажимает кнопку поле со списком.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*pWnd*<br/>
[in] Указатель на родительское окно кнопки поля со списком.  
  
*bDelay*<br/>
[in] Зарезервировано для использования в производном классе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод обрабатывает событие; в противном случае — значение FALSE.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarComboBoxButton::OnCtlColor  
 Вызывается платформой, когда пользователь изменяет цвет панели родительского задать цвет кнопки в поле со списком.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Контекст устройства, отображается кнопка поле со списком.  
  
*nCtlColor*<br/>
[in] Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор кисть, которая инфраструктура использует для рисования фона кнопки поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Этот метод также задает цвет текста кнопки поля со списком.  
  
##  <a name="ondraw"></a>  CMFCToolBarComboBoxButton::OnDraw  
 Вызывается платформой для отрисовки кнопки поля со списком, используя указанный стили и параметры.  
  
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
*Основного контроллера домена*<br/>
[in] Контекст устройства, которое отображает кнопки.  
  
*Rect*<br/>
[in] Ограничивающий прямоугольник кнопки.  
  
*pImages*<br/>
[in] Коллекция изображений, связанный с кнопкой.  
  
*bHorz*<br/>
[in] Состояние закрепления панели инструментов родительского. Значение TRUE, если закрепления панели инструментов по горизонтали и FALSE при вертикально закрепления панели инструментов.  
  
*bCustomizeMode*<br/>
[in] Находится ли приложение в режим настройки.  
  
*bHighlight*<br/>
[in] Нужно ли Рисование выделенной кнопкой поле со списком.  
  
*bDrawBorder*<br/>
[in] Следует ли рисовать кнопка поле со списком с границей.  
  
*bGrayDisabledButtons*<br/>
[in] Значение true, чтобы нарисовать тень кнопки; Значение FALSE, чтобы использовать коллекцию изображений отключено.  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 Вызывается платформой для отображения кнопки поля со списком в **команды** области **Настройка** диалоговое окно.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Контекст устройства, отображается кнопка поле со списком.  
  
*Rect*<br/>
[in] Ограничивающий прямоугольник кнопки поля со списком.  
  
*bSelected*<br/>
[in] Значение TRUE, если выбрано поле со списком; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина в пикселях, кнопки поля со списком.  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 Вызывается платформой для задания поля со списком Шрифт кнопка, при изменении шрифта приложения.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="onmove"></a>  CMFCToolBarComboBoxButton::OnMove  
 Вызывается платформой для изменения расположения, кнопки поля со списком при перемещении родительской панели инструментов.  
  
```  
virtual void OnMove();
```  
  
##  <a name="onshow"></a>  CMFCToolBarComboBoxButton::OnShow  
 Вызывается платформой при скрытии или отображении кнопки поля со списком.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
*bShow*<br/>
[in] Следует ли скрывать и отображать кнопку поле со списком.  
  
##  <a name="onsize"></a>  CMFCToolBarComboBoxButton::OnSize  
 Вызывается платформой для изменения размера кнопки поля со списком, изменении размера родительской панели инструментов.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Параметры  
*iSize*<br/>
[in] Новая ширина кнопки поля со списком.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarComboBoxButton::OnUpdateToolTip  
 Вызывается платформой, когда пользователь изменяет всплывающей подсказки для кнопки поля со списком.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
*pWndParent*<br/>
[in] Указатель на родительское окно кнопки поля со списком.  
  
*iButtonIndex*<br/>
[in] Идентификатор кнопки поля со списком.  
  
*wndToolTip*<br/>
[in] Всплывающая подсказка, связываемое с кнопкой "поле со списком.  
  
*str*<br/>
[in] Текст подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод обрабатывает событие; в противном случае — значение FALSE.  
  
##  <a name="removeallitems"></a>  CMFCToolBarComboBoxButton::RemoveAllItems  
 Удаляет все элементы из поля списка и редактирования.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет все элементы из списка, поле и элемент управления списком.  
  
##  <a name="selectitem"></a>  CMFCToolBarComboBoxButton::SelectItem  
 Выбирает элемент в поле со списком.  
  
```  
BOOL SelectItem(
    int iIndex,  
    BOOL bNotify=TRUE);  
  
BOOL SelectItem(DWORD_PTR dwData);  
BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.  
  
*bNotify*<br/>
[in] Значение TRUE, чтобы уведомить кнопки поля со списком выделения; в противном случае — значение FALSE.  
  
*dwData*<br/>
[in] Данные, связанные с элементом в поле со списком.  
  
*lpszText*<br/>
[in] Текст элемента в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="selectitemall"></a>  CMFCToolBarComboBoxButton::SelectItemAll  
 Выбирает элемент в списке кнопки поля со списком с указанным идентификатором команды.  
  
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
*uiCmd*<br/>
[in] Идентификатор команды, кнопки поля со списком, которая содержит поле со списком.  
  
*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком. Значение -1, удаляет любое текущее выделение в поле со списком и очищает поля ввода.  
  
*dwData*<br/>
[in] Данные элемента в поле со списком.  
  
*lpszText*<br/>
[in] Текст элемента в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="serialize"></a>  CMFCToolBarComboBoxButton::Serialize  
 Считывает этот объект из архива или записывает его в архив.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
*ar*<br/>
[in, out] `CArchive` Объект для сериализации.  
  
### <a name="remarks"></a>Примечания  
 Параметры в `CArchive` объекта определить, является ли этот метод считывает или записывает в архив.  
  
##  <a name="setaccdata"></a>  CMFCToolBarComboBoxButton::SetACCData  
 Заполняет указанный `CAccessibilityData` объекта, используя данные специальных возможностей с помощью кнопки поля со списком.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
*pParent*<br/>
[in] Родительское окно кнопки поля со списком.  
  
*data*<br/>
[out] Объект `CAccessibilityData` объект, получающий данные специальных возможностей с помощью кнопки поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.  
  
##  <a name="setcentervert"></a>  CMFCToolBarComboBoxButton::SetCenterVert  
 Задает вертикальное положение кнопки поля со списком в приложении.  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*bCenterVert*<br/>
[in] Значение TRUE, чтобы Отцентрируйте кнопку поле со списком на панели инструментов; Значение FALSE, чтобы кнопка выровнена относительно кнопки поля со списком в верхней части панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию кнопки поля со списком выравниваются по верхней.  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarComboBoxButton::SetContextMenuID  
 Задает идентификатор ресурса контекстное меню для поля со списком кнопку в окне.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Параметры  
*uiResID*<br/>
[in] Идентификатор контекстного меню ресурса.  
  
##  <a name="setdropdownheight"></a>  CMFCToolBarComboBoxButton::SetDropDownHeight  
 Задает высоту элемента поле со списком при его удалении.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
*nHeight*<br/>
[in] Высота в пикселях поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Высота по умолчанию — 150 пикселей.  
  
##  <a name="setflatmode"></a>  CMFCToolBarComboBoxButton::SetFlatMode  
 Задает плоский внешний вид кнопок поле со списком в приложении.  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*bFlat*<br/>
[in] Значение TRUE для плоский внешний вид; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Плоский стиль по умолчанию для кнопок поле со списком имеет значение FALSE.  
  
##  <a name="setstyle"></a>  CMFCToolBarComboBoxButton::SetStyle  
 Задает указанный стиль для поля со списком кнопку в окне и перерисовывает элемент управления, если она не отключена.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
*nStyle*<br/>
[in] Побитовое сочетание (OR) стили панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Список стили кнопок панели инструментов см. в разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="settext"></a>  CMFCToolBarComboBoxButton::SetText  
 Задает текст в поле ввода поля со списком кнопку в окне.  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
*lpszText*<br/>
[in] Указатель на строку, которая содержит текст для поля ввода.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)



