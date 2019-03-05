---
title: Класс CVSListBox
ms.date: 11/19/2018
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
ms.openlocfilehash: 618f4f386db477dd301ada862ebd2094a6c6651f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301524"
---
# <a name="cvslistbox-class"></a>Класс CVSListBox

`CVSListBox` Класс поддерживает элемент управления редактирования списка.

## <a name="syntax"></a>Синтаксис

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CVSListBox::CVSListBox](#cvslistbox)|Создает объект `CVSListBox`.|
|`CVSListBox::~CVSListBox`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CVSListBox::AddItem](#additem)|Добавляет строку в элементе управления списком. (Переопределяет `CVSListBoxBase::AddItem`.)|
|[CVSListBox::EditItem](#edititem)|Начинает операцию изменения текста элемента управления списка. (Переопределяет `CVSListBoxBase::EditItem`.)|
|[CVSListBox::GetCount](#getcount)|Возвращает число строк в элементе управления редактирования списка. (Переопределяет `CVSListBoxBase::GetCount`.)|
|[CVSListBox::GetItemData](#getitemdata)|Извлекает значение 32-разрядных конкретного приложения, связанный с элементом управления Изменяемый список. (Переопределяет `CVSListBoxBase::GetItemData`.)|
|[CVSListBox::GetItemText](#getitemtext)|Получает текст элемента управления редактирования списка. (Переопределяет `CVSListBoxBase::GetItemText`.)|
|[CVSListBox::GetSelItem](#getselitem)|Получает отсчитываемый от нуля индекс выбранного элемента в элементе управления редактирования списка. (Переопределяет `CVSListBoxBase::GetSelItem`.)|
|`CVSListBox::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) функции Windows. Дополнительные сведения и синтаксис методов, см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CVSListBoxBase::PreTranslateMessage`.)|
|[CVSListBox::RemoveItem](#removeitem)|Удаляет элемент из элемента управления редактирования списка. (Переопределяет `CVSListBoxBase::RemoveItem`.)|
|[CVSListBox::SelectItem](#selectitem)|Выбирает строку элемента управления редактирования списка. (Переопределяет `CVSListBoxBase::SelectItem`.)|
|[CVSListBox::SetItemData](#setitemdata)|Связывает значение 32-разрядных конкретного приложения с редактируемого элемента управления элемента списка. (Переопределяет `CVSListBoxBase::SetItemData`.)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|Возвращает дескриптор текущего элемента управления представления внедренным списком.|

## <a name="remarks"></a>Примечания

`CVSListBox` Класс предоставляет набор кнопок редактирования, пользователь мог создать, изменить, удалить или изменить порядок элементов в элементе управления списком.

Ниже приведен рисунок редактирования элемента управления. Вторая запись списка, который называется «Item2», выбран для редактирования.

![Элемент управления CVSListBox](../../mfc/reference/media/cvslistbox.png "управления CVSListBox")

При использовании редактора ресурсов для добавления элемента управления редактирования списка, обратите внимание, что **элементов** панели редактора не поддерживает элемент управления стандартного списка редактируемой. Вместо этого добавьте статический элемент управления, такие как **группа** элемента управления. Инфраструктура использует статический элемент управления как заполнитель, чтобы указать размер и положение элемента управления редактирования списка.

Чтобы использовать элемент управления редактирования списка в шаблон диалогового окна, объявите `CVSListBox` переменной в классе диалогового окна. Для поддержки обмена данными между переменной и элемент управления, определить `DDX_Control` запись макроса в `DoDataExchange` метод диалогового окна. По умолчанию элемент управления редактирования списка создается без кнопки изменения. Метод унаследованные CVSListBoxBase::SetStandardButtons для включения кнопки изменения.

Дополнительные сведения см. в каталог образцов, `New Controls` пример Page3.cpp и Page3.h файлы.

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

Добавляет строку в элементе управления списком.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>Параметры

*strIext*<br/>
[in] Ссылка на строку.

*dwData*<br/>
[in] Значение 32-разрядных конкретного приложения, связанный со строкой. Значение по умолчанию — 0.

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс позиции, которая будет содержать строки. Если *iIndex* параметр имеет значение -1, строка добавляется в конец списка. Значение по умолчанию — -1.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс позиции строки в элементе управления списком.

### <a name="remarks"></a>Примечания

Используйте [CVSListBox::GetItemData](#getitemdata) метод для получения значения, который задается параметром *dwData* параметра. Это значение может быть целое число от приложения или указатель на другие данные.

##  <a name="cvslistbox"></a>  CVSListBox::CVSListBox

Создает объект `CVSListBox`.

```
CVSListBox();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="edititem"></a>  CVSListBox::EditItem

Начинает операцию изменения текста элемента управления списка.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента управления списка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если операция редактирования запускается успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Пользователь начинает операцию изменения, дважды щелкнув метку элемента или нажимая клавиши **F2** или **пробел** ключа, если элемент имеет фокус.

##  <a name="getcount"></a>  CVSListBox::GetCount

Возвращает число строк в элементе управления редактирования списка.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в элементе управления "Список".

### <a name="remarks"></a>Примечания

Обратите внимание, что счетчик 1 больше, чем значение индекса последнего элемента, так как индекс отсчитывается от нуля.

##  <a name="getitemdata"></a>  CVSListBox::GetItemData

Извлекает значение 32-разрядных конкретного приложения, связанный с элементом управления Изменяемый список.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс редактируемого элемента управления элемента списка.

### <a name="return-value"></a>Возвращаемое значение

32-разрядное значение, связанный с указанным элементом.

### <a name="remarks"></a>Примечания

Используйте [CVSListBox::SetItemData](#setitemdata) или [CVSListBox::AddItem](#additem) метода, чтобы установить 32-разрядное значение с элементом управления списка. Это значение может быть целое число от приложения или указатель на другие данные.

##  <a name="getitemtext"></a>  CVSListBox::GetItemText

Получает текст элемента управления редактирования списка.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс редактируемого элемента управления элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, содержащего текст указанного элемента.

### <a name="remarks"></a>Примечания

##  <a name="getlisthwnd"></a>  CVSListBox::GetListHwnd

Возвращает дескриптор текущего элемента управления представления внедренным списком.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор управления представления списком embedded.

### <a name="remarks"></a>Примечания

Используйте этот метод для получения дескриптора элемента управления представления внедренным списком, который поддерживает `CVSListBox` класса.

##  <a name="getselitem"></a>  CVSListBox::GetSelItem

Получает отсчитываемый от нуля индекс выбранного элемента в элементе управления редактирования списка.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если этот метод выполнен успешно, отсчитываемый от нуля индекс выбранного элемента; в противном случае — значение -1.

### <a name="remarks"></a>Примечания

##  <a name="removeitem"></a>  CVSListBox::RemoveItem

Удаляет элемент из элемента управления редактирования списка.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс редактируемого элемента управления элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанный элемент удален; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="selectitem"></a>  CVSListBox::SelectItem

Выбирает строку элемента управления редактирования списка.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>Параметры

*iItem*<br/>
[in] Отсчитываемый от нуля индекс редактируемого элемента управления элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод выбирает указанный элемент и при необходимости, прокручивает элемент в представлении.

##  <a name="setitemdata"></a>  CVSListBox::SetItemData

Связывает значение 32-разрядных конкретного приложения с редактируемого элемента управления элемента списка.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс редактируемого элемента управления элемента списка.

*dwData*<br/>
[in] 32-разрядное значение. Это значение может быть целое число от приложения или указатель на другие данные.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
