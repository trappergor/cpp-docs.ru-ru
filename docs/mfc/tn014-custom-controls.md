---
title: 'TN014: Пользовательские элементы управления'
ms.date: 06/28/2018
f1_keywords:
- vc.controls
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
ms.openlocfilehash: c68b60f065e69213b3ab32c887bc7af129a70fef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306224"
---
# <a name="tn014-custom-controls"></a>TN014: Пользовательские элементы управления

Эта заметка описывает поддержку MFC для пользовательских и самостоятельно рисования элементов управления. Он также описывает динамического создания подклассов, а связь между [CWnd](../mfc/reference/cwnd-class.md) объектов и `HWND`s.

Пример приложения MFC CTRLTEST показано, как использовать многие пользовательские элементы управления. Ознакомьтесь с исходным кодом примера MFC Общие [CTRLTEST](../overview/visual-cpp-samples.md) и Справка в Интернете.

## <a name="owner-draw-controlsmenus"></a>Владельцем элементов управления и меню

Windows обеспечивает поддержку пользовательской отрисовки элементов управления и меню с помощью сообщений Windows. Родительское окно любого элемента управления или меню получает эти сообщения и вызовы функции в ответ. Вы можете переопределить эти функции, чтобы настроить внешний вид и поведение, рисуемый владельцем элемент управления или меню.

MFC поддерживает рисуемого владельцем со следующими функциями:

- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

Вы можете переопределить эти функции в вашей `CWnd` производный класс для реализации поведения настраиваемой отрисовки.

Этот подход не приводит к повторно используемого кода. При наличии двух схожих элементов управления в двух разных `CWnd` классов, необходимо реализовать поведение пользовательского элемента управления в двух местах. Архитектура поддерживается MFC самостоятельно рисования элементов управления решает эту проблему.

## <a name="self-draw-controls-and-menus"></a>Самостоятельно рисования элементов управления и меню

MFC предоставляет реализацию по умолчанию (в `CWnd` и [CMenu](../mfc/reference/cmenu-class.md) классы) для сообщений о стандартной пользовательской отрисовки. Эта реализация по умолчанию будет декодировать параметры пользовательской отрисовки и делегировать сообщения рисования владельцем элементов управления или меню. Это называется самостоятельно нарисовать так, как код прорисовки находится в классе элемента управления или меню, не в окно-владелец.

С помощью самостоятельно рисования элементов управления можно создавать классы многократного использования элемента управления, которые используют семантику пользовательской отрисовки для отображения элемента управления. Код для рисования элемента управления находится в классе элемента управления, а не его родительским элементом. Это объектно ориентированного подхода к программированию пользовательского элемента управления. Добавьте следующий список функций в пользовательские классы самостоятельно нарисовать:

- Для кнопок, рисования самостоятельно:

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- Для рисования самостоятельно меню:

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- Самостоятельно нарисовать списков:

    ```cpp
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this list box
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this list box

    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this list box if LBS_SORT
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this list box
    ```

- Самостоятельно нарисовать списком:

    ```cpp
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this combo box
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this combo box

    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this combo box if CBS_SORT
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this combo box
    ```

Дополнительные сведения о структуре пользовательской отрисовки ([DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct), [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct), [COMPAREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcompareitemstruct), и [DELETEITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdeleteitemstruct)) см. в документации MFC `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, и `CWnd::OnDeleteItem` соответственно.

## <a name="using-self-draw-controls-and-menus"></a>С помощью самостоятельно рисования элементов управления и меню

Для рисования самостоятельно меню, необходимо переопределить `OnMeasureItem` и `OnDrawItem` методы.

Для списка самостоятельно нарисовать и выпадающие списки, необходимо переопределить `OnMeasureItem` и `OnDrawItem`. Необходимо указать стиль LBS_OWNERDRAWVARIABLE для списков или CBS_OWNERDRAWVARIABLE стиль поля со списком в шаблон диалогового окна. Стиль OWNERDRAWFIXED не будет работать с самостоятельно рисовать элементы, поскольку высоты основного элемента определяется, прежде чем вложенные самостоятельно рисования элементов управления в поле со списком. (Можно использовать методы [CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) и [CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) Чтобы преодолеть это ограничение.)

Переключение на стиль OWNERDRAWVARIABLE приведет к системе для применения стиля NOINTEGRALHEIGHT к элементу управления. Так как элемент управления не удается вычислить Общая высота с переменной размера элементов, стиль по умолчанию INTEGRALHEIGHT игнорируется и элемент управления всегда NOINTEGRALHEIGHT. Закрепление высота элементов можно предотвратить части элементов изображаемого, указав размер элемента управления между резервными целое число и размер элемента.

Для самостоятельной рисования, списки и поля со списком в стиле LBS_SORT или CBS_SORT, необходимо переопределить `OnCompareItem` метод.

Для рисования самостоятельно, списками и списками, `OnDeleteItem` обычно не переопределяется. Можно переопределить `OnDeleteItem` Если вы хотите выполнять специальную обработку. Один случай, где это было бы применимо — дополнительную память или другие ресурсы хранятся с каждым элементом списка или поля со списком поле.

## <a name="examples-of-self-drawing-controls-and-menus"></a>Примеры самостоятельно графических элементов управления и меню

Пример MFC Общие [CTRLTEST](../overview/visual-cpp-samples.md) примеры меню самостоятельно нарисовать и самостоятельно нарисовать список.

Наиболее типичным примером самостоятельно рисования кнопки — это кнопка растрового изображения. Кнопка растрового изображения является кнопку для показа одного, двух или трех растровых изображений для различных состояний. Примером этого предоставляется в классе MFC [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).

## <a name="dynamic-subclassing"></a>Динамическое создание подклассов

Иногда требуется изменить функциональность объекта, который уже существует. Приведенные выше примеры нужно было настраивать элементы управления, прежде чем они были созданы. Динамическое создание подклассов позволяет настраивать элемент управления, который уже был создан.

Создание подклассов является термин Windows для замены <xref:System.Windows.Forms.Control.WndProc%2A> окна с настраиваемый `WndProc` и вызов старый `WndProc` для функциональные возможности по умолчанию.

Это не следует путать с помощью наследования классов C++. Для пояснения рассмотрим условия C++ *базового класса* и *производный класс* аналогичны *суперкласса* и *подкласс* в Windows Объектная модель. Наследования C++ с MFC и Windows подклассы функционально похожи, за исключением C++ не поддерживает динамическое создание подклассов.

`CWnd` Класс предоставляет соединение между объектом C++ (производный от `CWnd`) и объект окна Windows (известный как `HWND`).

Существуют три распространенных способа, которыми они связаны:

- `CWnd` Создает `HWND`. Можно изменить поведение в производном классе, создав класс, производный от `CWnd`. `HWND` Создается, когда приложение вызывает [CWnd::Create](../mfc/reference/cwnd-class.md#create).

- Приложение присоединяет `CWnd` к существующему `HWND`. Поведение существующее окно не изменяется. Это — это случай делегирования и стало возможным, вызвав [CWnd::Attach](../mfc/reference/cwnd-class.md#attach) псевдоним существующий `HWND` для `CWnd` объекта.

- `CWnd` присоединен к существующему `HWND` и вы можете изменить поведение в производном классе. Это называется динамическое создание подкласса, так как мы изменяем поведение и, следовательно, класс объекта Windows во время выполнения.

Динамическое создание подклассов можно добиться с помощью методов [CWnd::SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) и[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem).

Присоединить оба подпрограммы `CWnd` объекта к существующему `HWND`. `SubclassWindow` принимает `HWND` напрямую. `SubclassDlgItem` — это вспомогательная функция, которая принимает идентификатор элемента управления и родительского окна. `SubclassDlgItem` предназначен для присоединения объектов C++ к элементам управления диалогового окна, созданные на основе шаблона диалогового окна.

См. в разделе [CTRLTEST](../overview/visual-cpp-samples.md) примере некоторые примеры использования `SubclassWindow` и `SubclassDlgItem`.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
