---
title: Класс CVSListBox | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
dev_langs:
- C++
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 380b470531fd28d8cfe68aa931105430111c3dbf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cvslistbox-class"></a>Класс CVSListBox
`CVSListBox` Класс поддерживает элемент управления для редактирования списка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](#cvslistbox)|Создает объект `CVSListBox`.|  
|`CVSListBox::~CVSListBox`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CVSListBox::AddItem](#additem)|Добавляет строку в элементе списка. (Переопределяет `CVSListBoxBase::AddItem`.)|  
|[CVSListBox::EditItem](#edititem)|Запускает операцию изменения в тексте элемента управления списка. (Переопределяет `CVSListBoxBase::EditItem`.)|  
|[CVSListBox::GetCount](#getcount)|Возвращает число строк в элементе управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetCount`.)|  
|[CVSListBox::GetItemData](#getitemdata)|Возвращает 32-разрядное значение конкретного приложения, связанный с элементом управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetItemData`.)|  
|[CVSListBox::GetItemText](#getitemtext)|Извлекает текст элемента управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetItemText`.)|  
|[CVSListBox::GetSelItem](#getselitem)|Возвращает отсчитываемый от нуля индекс выбранного элемента в элементе управления для редактирования списка. (Переопределяет `CVSListBoxBase::GetSelItem`.)|  
|`CVSListBox::PreTranslateMessage`|Преобразует сообщения окна перед их передачей [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Дополнительные сведения и синтаксис методов см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CVSListBoxBase::PreTranslateMessage`.)|  
|[CVSListBox::RemoveItem](#removeitem)|Удаляет элемент из элемента управления для редактирования списка. (Переопределяет `CVSListBoxBase::RemoveItem`.)|  
|[CVSListBox::SelectItem](#selectitem)|Выбирает строку элемента управления для редактирования списка. (Переопределяет `CVSListBoxBase::SelectItem`.)|  
|[CVSListBox::SetItemData](#setitemdata)|32-разрядное значение приложении связывает с элементом управления для редактирования списка. (Переопределяет `CVSListBoxBase::SetItemData`.)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](#getlisthwnd)|Возвращает дескриптор текущего элемента управления представления внедренный список.|  
  
## <a name="remarks"></a>Примечания  
 `CVSListBox` Класс предоставляет набор редактирование кнопок, которые позволяют пользователю создать, изменить, удалить или изменить порядок элементов в элементе управления списком.  
  
 Ниже приведен рисунка для редактирования элемента управления. Второй список запись, которая называется «Item2», выбранной для редактирования.  
  
 ![Элемент управления CVSListBox](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 При использовании редактора ресурсов для добавления элемента управления для редактирования списка, обратите внимание, что **элементов** панели редактора не предоставляет элемент управления стандартного списка для редактирования. Вместо этого добавьте статический элемент управления, такие как **группа** элемента управления. Платформа использует статический элемент управления как заполнитель, чтобы указать размер и положение элемента управления для редактирования списка.  
  
 Чтобы использовать элемент управления для редактирования списка в шаблон диалогового окна, объявите `CVSListBox` переменной в классе диалогового окна. Для поддержки обмена данными между переменной и элемента управления необходимо определить `DDX_Control` запись макроса в `DoDataExchange` метод диалогового окна. По умолчанию элемент управления для редактирования списка создается без кнопок изменения. Метод наследуемые CVSListBoxBase::SetStandardButtons для включения кнопки редактирования.  
  
 Дополнительные сведения см. в разделе каталог образцов, `New Controls` образцы файлов Page3.cpp и Page3.h.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxvslistbox.h  
  
##  <a name="additem"></a>  CVSListBox::AddItem  
 Добавляет строку в элементе списка.  
  
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
 Значение 32-разрядных конкретного приложения, связанного со строкой. Значение по умолчанию — 0.  
  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс позиции, которые будут храниться в строке. Если `iIndex` параметр имеет значение -1, строка добавляется в конец списка. Значение по умолчанию — -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс позиции строки в элементе управления списком.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CVSListBox::GetItemData](#getitemdata) метод для получения значения, который задается параметром `dwData` параметр. Это значение может быть целое число от приложения или указатель на другие данные.  
  
##  <a name="cvslistbox"></a>  CVSListBox::CVSListBox  
 Создает объект `CVSListBox`.  
  
```  
CVSListBox();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="edititem"></a>  CVSListBox::EditItem  
 Запускает операцию изменения в тексте элемента управления списка.  
  
```  
virtual BOOL EditItem(int iIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента управления списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если операция редактирования запускается успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Пользователь начинает операцию редактирования двойным щелчком метки элемента или нажав **F2** или **пробел** ключа, когда элемент имеет фокус.  
  
##  <a name="getcount"></a>  CVSListBox::GetCount  
 Возвращает число строк в элементе управления для редактирования списка.  
  
```  
virtual int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в элементе управления "Список".  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что счетчик на единицу больше, чем значение индекса последнего элемента, так как индекс начинается с нуля.  
  
##  <a name="getitemdata"></a>  CVSListBox::GetItemData  
 Возвращает 32-разрядное значение конкретного приложения, связанный с элементом управления для редактирования списка.  
  
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
  
##  <a name="getitemtext"></a>  CVSListBox::GetItemText  
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
  
##  <a name="getlisthwnd"></a>  CVSListBox::GetListHwnd  
 Возвращает дескриптор текущего элемента управления представления внедренный список.  
  
```  
virtual HWND GetListHwnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента управления внедренных списком.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для получения дескриптора элемента управления представления внедренный список, который поддерживает `CVSListBox` класса.  
  
##  <a name="getselitem"></a>  CVSListBox::GetSelItem  
 Возвращает отсчитываемый от нуля индекс выбранного элемента в элементе управления для редактирования списка.  
  
```  
virtual int GetSelItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если этот метод прошла успешно, отсчитываемый от нуля индекс текущего выделенного элемента; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removeitem"></a>  CVSListBox::RemoveItem  
 Удаляет элемент из элемента управления для редактирования списка.  
  
```  
virtual BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента управления для редактирования списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если указанный элемент был удален. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="selectitem"></a>  CVSListBox::SelectItem  
 Выбирает строку элемента управления для редактирования списка.  
  
```  
virtual BOOL SelectItem(int iItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iItem`  
 Отсчитываемый от нуля индекс элемента управления для редактирования списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выбирает указанный элемент и при необходимости, прокручивает элемент в представлении.  
  
##  <a name="setitemdata"></a>  CVSListBox::SetItemData  
 32-разрядное значение приложении связывает с элементом управления для редактирования списка.  
  
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
