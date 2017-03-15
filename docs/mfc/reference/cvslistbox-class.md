---
title: "Класс CVSListBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CVSListBox
dev_langs:
- C++
helpviewer_keywords:
- CVSListBox::PreTranslateMessage method
- CVSListBox class
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4527249fc1a22a1db0623ea46954065fcbd071f4
ms.lasthandoff: 02/24/2017

---
# <a name="cvslistbox-class"></a>Класс CVSListBox
`CVSListBox` Класс поддерживает элемент управления для редактирования списка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](#cvslistbox)|Создает объект `CVSListBox`.|  
|`CVSListBox::~CVSListBox`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CVSListBox::AddItem](#additem)|Добавляет строку в элементе управления списком. (Переопределяет `CVSListBoxBase::AddItem`.)|  
|[CVSListBox::EditItem](#edititem)|Запускает операцию изменения в тексте элемента управления списка. (Переопределяет `CVSListBoxBase::EditItem`.)|  
|[CVSListBox::GetCount](#getcount)|Получает число строк в элементе управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetCount`.)|  
|[CVSListBox::GetItemData](#getitemdata)|Извлекает значение 32-разрядные приложения, связанный с элементом управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetItemData`.)|  
|[CVSListBox::GetItemText](#getitemtext)|Извлекает текст элемента управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetItemText`.)|  
|[CVSListBox::GetSelItem](#getselitem)|Возвращает отсчитываемый от нуля индекс текущего выделенного элемента в элементе управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetSelItem`.)|  
|`CVSListBox::PreTranslateMessage`|Преобразует оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Дополнительные сведения и синтаксиса см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CVSListBoxBase::PreTranslateMessage`.)|  
|[CVSListBox::RemoveItem](#removeitem)|Удаляет элемент из списка для редактирования элемента управления. (Переопределяет `CVSListBoxBase::RemoveItem`.)|  
|[CVSListBox::SelectItem](#selectitem)|Выбирает строку элемента управления для редактирования списка. (Переопределяет `CVSListBoxBase::SelectItem`.)|  
|[CVSListBox::SetItemData](#setitemdata)|Связывает значение 32-разрядные приложения с элементом управления для редактирования списка. (Переопределяет `CVSListBoxBase::SetItemData`.)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](#getlisthwnd)|Возвращает дескриптор текущего элемента управления представления списка embedded.|  
  
## <a name="remarks"></a>Примечания  
 `CVSListBox` Класс предоставляет набор кнопок редактирования, позволяющие создать, изменить, удалить или изменить порядок элементов в элементе управления списком.  
  
 Ниже приведен рисунка для редактирования элемента управления. Второй список запись, которая называется «Item2», выбранных для редактирования.  
  
 ![Элемент управления CVSListBox](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 При использовании редактора ресурсов для добавления элемента управления для редактирования списка, обратите внимание, что **элементов** области редактора не предоставляет предварительно определенного списка для редактирования элемента управления. Вместо этого добавьте статический элемент управления, таких как **группа** элемента управления. Платформа использует статический элемент управления как заполнитель, чтобы указать размер и положение элемента управления для редактирования списка.  
  
 Чтобы использовать элемент управления для редактирования списка в шаблон диалогового окна, объявите `CVSListBox` переменной в классе диалогового окна. Для поддержки обмена данными между переменной и элемента управления, определить `DDX_Control` запись макроса в `DoDataExchange` метод диалогового окна. По умолчанию элемент управления для редактирования списка создается без кнопки изменения. Чтобы включить кнопки edit используйте унаследованного метода CVSListBoxBase::SetStandardButtons.  
  
 Дополнительные сведения см. в каталоге образцов `New Controls` образцы, файлы Page3.cpp и Page3.h.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxvslistbox.h  
  
##  <a name="a-nameadditema--cvslistboxadditem"></a><a name="additem"></a>CVSListBox::AddItem  
 Добавляет строку в элементе управления списком.  
  
```  
virtual int AddItem(
    const CString& strIext,  
    DWORD_PTR dwData=0,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strIext`  
 Ссылка на строку.  
  
 [in] `dwData`  
 Значение 32-разрядные приложения, связанного со строкой. Значение по умолчанию — 0.  
  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс позиции, который будет содержать строку. Если `iIndex` параметр имеет значение -1, строка добавляется в конец списка. Значение по умолчанию — -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс позиции строки в элементе управления списком.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CVSListBox::GetItemData](#getitemdata) метод для получения значения, который задается параметром `dwData` параметр. Это значение может быть целое число от приложения или указатель на другие данные.  
  
##  <a name="a-namecvslistboxa--cvslistboxcvslistbox"></a><a name="cvslistbox"></a>CVSListBox::CVSListBox  
 Создает объект `CVSListBox`.  
  
```  
CVSListBox();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameedititema--cvslistboxedititem"></a><a name="edititem"></a>CVSListBox::EditItem  
 Запускает операцию изменения в тексте элемента управления списка.  
  
```  
virtual BOOL EditItem(int iIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента управления списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если операция редактирования запускается успешно. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Пользователь запускает операцию редактирования, дважды щелкнув метку элемента или нажав **F2** или **пробел** ключ, если элемент имеет фокус.  
  
##  <a name="a-namegetcounta--cvslistboxgetcount"></a><a name="getcount"></a>CVSListBox::GetCount  
 Получает число строк в элементе управления для редактирования списка.  
  
```  
virtual int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в элементе управления "Список".  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что значение счетчика единицу больше, чем значение индекса последнего элемента, так как индекс начинается с нуля.  
  
##  <a name="a-namegetitemdataa--cvslistboxgetitemdata"></a><a name="getitemdata"></a>CVSListBox::GetItemData  
 Извлекает значение 32-разрядные приложения, связанный с элементом управления для редактирования списка.  
  
```  
virtual DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента управления для редактирования списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение, связанный с указанным элементом.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CVSListBox::SetItemData](#setitemdata) или [CVSListBox::AddItem](#additem) метода, чтобы установить 32-разрядное значение с элементом управления списка. Это значение может быть целое число от приложения или указатель на другие данные.  
  
##  <a name="a-namegetitemtexta--cvslistboxgetitemtext"></a><a name="getitemtext"></a>CVSListBox::GetItemText  
 Извлекает текст элемента управления для редактирования списка.  
  
```  
virtual CString GetItemText(int iIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента управления для редактирования списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, содержащего текст указанного элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetlisthwnda--cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a>CVSListBox::GetListHwnd  
 Возвращает дескриптор текущего элемента управления представления списка embedded.  
  
```  
virtual HWND GetListHwnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента управления списком embedded.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для получения дескриптора для элемента управления списком внедренные, поддерживающий `CVSListBox` класса.  
  
##  <a name="a-namegetselitema--cvslistboxgetselitem"></a><a name="getselitem"></a>CVSListBox::GetSelItem  
 Возвращает отсчитываемый от нуля индекс текущего выделенного элемента в элементе управления для редактирования списка.  
  
```  
virtual int GetSelItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если этот метод выполнен успешно, отсчитываемый от нуля индекс элемента, выбранного в данный момент; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameremoveitema--cvslistboxremoveitem"></a><a name="removeitem"></a>CVSListBox::RemoveItem  
 Удаляет элемент из списка для редактирования элемента управления.  
  
```  
virtual BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента управления для редактирования списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанный элемент был удален. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameselectitema--cvslistboxselectitem"></a><a name="selectitem"></a>CVSListBox::SelectItem  
 Выбирает строку элемента управления для редактирования списка.  
  
```  
virtual BOOL SelectItem(int iItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iItem`  
 Отсчитываемый от нуля индекс элемента управления для редактирования списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выбирает указанный элемент и при необходимости, прокрутке элемента.  
  
##  <a name="a-namesetitemdataa--cvslistboxsetitemdata"></a><a name="setitemdata"></a>CVSListBox::SetItemData  
 Связывает значение 32-разрядные приложения с элементом управления для редактирования списка.  
  
```  
virtual void SetItemData(
    int iIndex,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента управления для редактирования списка.  
  
 [in] `dwData`  
 32-разрядное значение. Это значение может быть целое число от приложения или указатель на другие данные.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

