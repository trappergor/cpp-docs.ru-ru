---
title: "TN014: Пользовательские элементы управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.controls
dev_langs: C++
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4ffc4f26ed365673cdfb525c2bf3653827cc4ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tn014-custom-controls"></a>TN014. Пользовательские элементы управления
Эта заметка описывается поддержка MFC для пользовательских и самостоятельной рисования элементов управления. Он также описывает динамического создания подкласса и связь между [CWnd](../mfc/reference/cwnd-class.md) объектов и `HWND`s.  
  
 Образец приложения MFC CTRLTEST показано, как использовать многие пользовательские элементы управления. См. исходный код образца MFC Общие [CTRLTEST](../visual-cpp-samples.md) и справки в Интернете.  
  
## <a name="owner-draw-controlsmenus"></a>Рисуемый владельцем элементы управления или меню  
 Windows поддерживает рисуемый владельцем элементов управления и меню с помощью сообщений Windows. Родительское окно элемента управления или меню получает эти сообщения и вызовы функций в ответ. Можно переопределить эти функции, чтобы настроить внешний вид и поведение рисуемый владельцем элемент управления или меню.  
  
 MFC поддерживает непосредственно рисуемый владельцем со следующими функциями:  
  
- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)  
  
- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)  
  
- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)  
  
- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)  
  
 Можно переопределить эти функции в вашей `CWnd` производный класс для реализации поведения настраиваемой отрисовки.  
  
 Этот подход приводит к многократно используемого кода. При наличии двух схожих элементов управления в двух разных `CWnd` классов, необходимо реализовать поведение пользовательского элемента управления в двух местах. Архитектура поддерживается MFC самостоятельной рисования элементов управления решает эту проблему.  
  
## <a name="self-draw-controls-and-menus"></a>Самостоятельной рисования элементов управления и меню  
 MFC предоставляет реализацию по умолчанию (в `CWnd` и [CMenu](../mfc/reference/cmenu-class.md) классы) для сообщений рисования владельцем standard. Данная реализация по умолчанию будет расшифровать параметры рисуемый владельцем и делегировать сообщения рисуемый владельцем элементов управления или меню. Это называется самостоятельно нарисовать так как код прорисовки класс элемента управления или меню не в окно-владелец.  
  
 С помощью самостоятельной рисования элементов управления можно создавать классы для повторного использования элементов управления, с помощью семантики рисуемый владельцем отображения элемента управления. Код для рисования элемента управления находится в классе элементов управления, а не его родителем. Это объектно ориентированный подход к программированию пользовательского элемента управления. Добавьте следующий список функций самостоятельно нарисовать классов:  
  
-   Для самостоятельной рисования кнопки:  
  
 ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw this button  
 ```  
  
-   Для самостоятельной рисования меню:  
  
 ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this menu  
 ```  
  
-   Для самостоятельной рисования списков:  
  
 ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this list box  
 
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this list box  
 ```  
  
-   Для самостоятельной рисования поля со списком:  
  
 ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this combo box  
 
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this combo box  
 ```  
  
 Дополнительные сведения о структурах рисуемый владельцем ([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), и [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)) см. в документации MFC `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, и `CWnd::OnDeleteItem` соответственно.  
  
## <a name="using-self-draw-controls-and-menus"></a>С помощью самостоятельной рисования элементов управления и меню  
 Для самостоятельной рисования меню, необходимо переопределить `OnMeasureItem` и `OnDrawItem` методы.  
  
 Для самостоятельной рисования списки и поля со списком, необходимо переопределить `OnMeasureItem` и `OnDrawItem`. Необходимо указать `LBS_OWNERDRAWVARIABLE` стиля для списков или `CBS_OWNERDRAWVARIABLE` стиль поля со списком полей в шаблон диалогового окна. `OWNERDRAWFIXED` Стиль не будет работать с самостоятельной рисования элементов, так как высоты основного элемента определяется до присоединения самостоятельной рисования элементов управления в список. (Можно использовать методы [CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) и [CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) для обхода этого ограничения.)  
  
 Переключение на `OWNERDRAWVARIABLE` стиль приведет к системе для применения `NOINTEGRALHEIGHT` стиля к элементу управления. Так как элемент управления не удается вычислить Общая высота с переменной размера элементов, стиль по умолчанию `INTEGRALHEIGHT` игнорируется и элемент управления всегда `NOINTEGRALHEIGHT`. Закрепление высота элементов можно предотвратить неполных элементов отрисовывается, указав размер быть множитель целое число от размера элемента управления.  
  
 Для самостоятельной рисования списков и полей со списком `LBS_SORT` или `CBS_SORT` стилей, необходимо переопределить `OnCompareItem` метод.  
  
 Для самостоятельной рисования списки и поля со списком, `OnDeleteItem` обычно не переопределяется. Можно переопределить `OnDeleteItem` Если требуется для выполнения специальной обработки. Один вариант, где это было бы возможно при дополнительную память или другие ресурсы хранятся с каждым элементом списка или поля со списком поле.  
  
## <a name="examples-of-self-drawing-controls-and-menus"></a>Примеры самостоятельной рисования элементов управления и меню  
 Пример MFC Общие [CTRLTEST](../visual-cpp-samples.md) приводятся образцы меню самостоятельной рисования и самостоятельно нарисовать список.  
  
 Наиболее типичным примером кнопку самостоятельной рисования — это кнопка растрового изображения. Битовая карта кнопка является кнопкой, показывающий одного, двух или трех растровых изображений для различных состояний. Пример этого приведен в класс MFC [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).  
  
## <a name="dynamic-subclassing"></a>Динамическое создание подклассов  
 Иногда требуется изменить функциональность объекта, который уже существует. Приведенные выше примеры необходимые для настройки элементов управления, прежде чем они были созданы. Динамическое создание подклассов позволяет настраивать элемент управления, который уже был создан.  
  
 Создание подклассов — это термин Windows для замены [WndProc](http://msdn.microsoft.com/en-us/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26) окна с настраиваемый `WndProc` и вызов старый `WndProc` для функциональных возможностей по умолчанию.  
  
 Это не следует путать с производного класса C++. Для дополнительной информации, условия C++ *базового класса* и *производного класса* аналогичны *суперкласса* и *подкласс* в Windows Объектная модель. Наследования C++ с MFC и Windows подклассы функционально похожи, за исключением C++ не поддерживает динамическое создание подклассов.  
  
 `CWnd` Класс обеспечивает подключение между объекта C++ (производный от `CWnd`) и объект окна Windows (известный как `HWND`).  
  
 Существует три общих способа, которыми они связаны:  
  
- `CWnd`Создает `HWND`. Можно изменить поведение в производном классе, создав класс, производный от `CWnd`. `HWND` Создается, когда приложение вызывает [CWnd::Create](../mfc/reference/cwnd-class.md#create).  
  
-   Присоединяет приложения `CWnd` к существующему `HWND`. Поведение существующее окно не изменяется. Это происходит делегирования и стало возможным благодаря вызов [CWnd::Attach](../mfc/reference/cwnd-class.md#attach) в псевдоним существующий `HWND` для `CWnd` объекта.  
  
- `CWnd`присоединен к существующему `HWND` и можно изменить поведение в производном классе. Это называется динамическое создание подклассов, поскольку выполняется изменение поведения и, следовательно, класс объекта Windows во время выполнения.  
  
 Динамическое создание подклассов можно добиться с помощью методов [CWnd::SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) и[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem).  
  
 Подключите оба подпрограммы `CWnd` объекта к существующему `HWND`. `SubclassWindow`принимает `HWND` напрямую. `SubclassDlgItem`является вспомогательная функция, которая принимает идентификатор элемента управления и родительского окна. `SubclassDlgItem`предназначен для присоединения C++ объектов к элементам управления диалогового окна, созданные на основе шаблона диалогового окна.  
  
 В разделе [CTRLTEST](../visual-cpp-samples.md) примере некоторые примеры использования `SubclassWindow` и `SubclassDlgItem`.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

