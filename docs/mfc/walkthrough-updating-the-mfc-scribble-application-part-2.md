---
title: 'Пошаговое руководство: Обновление приложения MFC Scribble (часть 2) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83caf353ca4a45e3ae834a41062de955a91dbb8a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952441"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>Пошаговое руководство. Обновление приложения MFC Scribble (часть 2)
[Часть 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) этого пошагового руководства показано, как добавить ленту Office Fluent классической Scribble приложения. В этом разделе рассматриваются добавление панелей ленты и элементов управления, которые пользователи могут использовать вместо меню и команд.  
  
## <a name="prerequisites"></a>Предварительные требования  
 [Примеры кода на Visual C++](../visual-cpp-samples.md)  
  
##  <a name="top"></a> Разделы  
 В этой части пошагового руководства состоит из следующих подразделов:  
  
- [Добавление новых элементов управления на ленту](#addnewpanel)  
  
- [Добавление панель справки на ленту](#addhelppanel)  
  
- [Добавление панели пера на ленту](#addpenpanel)  
  
- [Добавление кнопки цвет на ленту](#addcolorbutton)  
  
- [Добавление члена цвет класс документа](#addcolormember)  
  
- [Инициализация перья и сохранение настроек](#initpensave)  
  
##  <a name="addnewpanel"></a> Добавление новых элементов управления на ленту  
 Следующие шаги показывают, как добавить **представление** панель, которая содержит два флажка, управляющие видимостью панели инструментов и строки состояния, а также **окна** панель, содержащую вертикально разбиения Кнопка, которая управляет созданием и расположении окон многодокументного интерфейса (MDI).  
  
#### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Чтобы добавить панели представления и окна панели на панель ленты  
  
1.  Создание панели с именем *представление*, который имеет два флажка, Переключить строку состояния и панель инструментов.  
  
    1.  Из **элементов**, перетащите **панель** для **Главная** категории. Затем перетащите два **флажки** панель.  
  
    2.  Щелкните панель, чтобы изменить его свойства. Изменение **заголовок** для *представление*.  
  
    3.  Щелкните первый флажок, чтобы изменить его свойства. Изменение **идентификатор** для *ID_VIEW_TOOLBAR* и **заголовок** для *инструментов*.  
  
    4.  Выберите второй флажок, чтобы изменить его свойства. Изменение **идентификатор** для *ID_VIEW_STATUS_BAR* и **заголовок** для *строка состояния*.  
  
2.  Создание панели с именем *окна* с разворачивающейся кнопки. При нажатии кнопки разделения контекстное меню отображаются три команды, которые уже определены в приложении Scribble.  
  
    1.  Из **элементов**, перетащите **панель** для **Главная** категории. Затем перетащите **кнопку** панель.  
  
    2.  Щелкните панель, чтобы изменить его свойства. Изменение **заголовок** для *окна*.  
  
    3.  Нажмите кнопку. Изменение **заголовок** для *Windows*, **ключей** для *w*, **индекс большого изображения** для *1* , и **режим разбиения** для *False*. Нажмите кнопку с многоточием (**...** ) рядом с **пунктов меню** Открытие **редактор элементов** диалоговое окно.  
  
    4.  Нажмите кнопку **добавить** три раза, чтобы добавить три кнопки.  
  
    5.  Нажмите кнопку «первый», а затем измените **заголовок** для *новое окно*, и **идентификатор** для *ID_WINDOW_NEW*.  
  
    6.  Нажмите вторую кнопку, а затем измените **заголовок** для *Cascade*, и **идентификатор** для *ID_WINDOW_CASCADE*.  
  
    7.  Щелкните третью кнопка и измените **заголовок** для *плитки*, и **идентификатор** для *ID_WINDOW_TILE_HORZ*.  
  
3.  Сохранить изменения и затем постройте и запустите приложение. **Представление** и **окна** панели должны отображаться. Нажмите кнопки, чтобы подтвердить правильность их.  
  
 [[Разделы](#top)]  
  
##  <a name="addhelppanel"></a> Добавление панель справки на ленту  
 Теперь можно назначить два элемента меню, которые определены в приложении Scribble для кнопки ленты, которые называются **разделы справки** и **об Scribble**. Кнопки добавляются в новую область с именем **справки**.  
  
#### <a name="to-add-a-help-panel"></a>Чтобы добавить панель справки  
  
1.  Из **элементов**, перетащите **панель** для **Главная** категории. Затем перетащите два **кнопки** панель.  
  
2.  Щелкните панель, чтобы изменить его свойства. Изменение **заголовок** для *справки*.  
  
3.  Нажмите первую кнопку. Изменение **заголовок** для *разделы справки*, и **идентификатор** для *ID_HELP_FINDER*.  
  
4.  Нажмите вторую кнопку. Изменение **заголовок** для *об Scribble...* , и **идентификатор** для *ID_APP_ABOUT*.  
  
5.  Сохранить изменения и затем постройте и запустите приложение. Объект **справки** отображать панель, которая содержит две кнопки на ленте.  
  
    > [!IMPORTANT]
    >  При нажатии кнопки **разделы справки** кнопки, приложение Scribble открывает сжатого файла справки HTML (.chm) с именем *your_project_name*. chm. Следовательно Если проект называется Scribble, необходимо переименовать файл справки на имя вашего проекта.  
  
 [[Разделы](#top)]  
  
##  <a name="addpenpanel"></a> Добавление панели пера на ленту  
 Теперь добавьте панель для отображения кнопок, которые управляют толщину и цвет пера. Эта панель содержит флажок, который выполняет переключение между перья толстой структуру и малый размер. Аналогично его функциональность **толстой линией** элемента меню в приложении Scribble.  
  
 В исходном приложении Scribble дает пользователю возможность выбирать ширину пера в диалоговом окне, которое появляется при нажатии **толщины** меню. Поскольку панель ленты имеет достаточно места для новых элементов управления, можно заменить диалоговое окно с помощью двух поля со списком на ленте. Одно поле со списком Корректирует ширину пера тонкой и поле со списком Корректирует ширину толстого пера.  
  
#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Чтобы добавить перо панель "и" поле со списком "на ленте  
  
1.  Из **элементов**, перетащите **панель** для **Главная** категории. Затем перетащите **флажок** и два **поля со списком** панель.  
  
2.  Щелкните панель, чтобы изменить его свойства. Изменение **заголовок** для *перо*.  
  
3.  Установите флажок. Изменение **заголовок** для *использовать толстая*, и **идентификатор** для *ID_PEN_THICK_OR_THIN*.  
  
4.  Щелкните в первом поле со списком. Изменение **заголовок** для *тонкой перо*, **идентификатор** для *ID_PEN_THIN_WIDTH*, **текст** для *2* , **Тип** для *раскрывающемся списке*, и **данные** для *1, 2 3; 4; 5; 6, 7, 8, 9;*.  
  
5.  Щелкните второе поле со списком. Изменение **заголовок** для *толстого пера*, **идентификатор** для *ID_PEN_THICK_WIDTH*, **текст** для  *5*, **тип** для *раскрывающемся списке*, и **данные** для *5, 6, 7; 8; 9; 10; 11; 12; 13; 14; 15; 16; 17; 18, 19, 20;*.  
  
6.  Новые поля со списком всех имеющихся элементов меню не соответствуют. Таким образом необходимо создать пункт меню для каждого параметра пера.  
  
    1.  В **представление ресурсов** окно, открыть ресурс меню IDR_SCRIBBTYPE.  
  
    2.  Нажмите кнопку **перо** открыть p**en** меню. Нажмите кнопку **введите здесь** и тип *вер & n перо*.  
  
    3.  Щелкните правой кнопкой мыши текст, который вы ввели откройте **свойства** окон, а затем изменить идентификатор свойство для *ID_PEN_THIN_WIDTH*.  
  
    4.  Также необходимо создать обработчик событий для всех элементов меню пера. Щелкните правой кнопкой мыши **вер & n перо** пункт меню, который вы только что создали и нажмите кнопку **добавить обработчик событий**. **Мастер обработчиков событий** отображается.  
  
    5.  В **список классов** поле в мастере выберите **CScribbleDoc** и нажмите кнопку **добавлять и редактировать**. При этом создается обработчик событий с именем `CScribbleDoc::OnPenThinWidth`.  
  
    6.  Добавьте следующий код к `CScribbleDoc::OnPenThinWidth`.  
  
 ``` *Получить указатель на ленту панели CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) -> GetRibbonBar(); ASSERT_VALID(pRibbon); */ / Получить указатель на поле со списком тонкой ширина CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox, pRibbon -> FindByID(ID_PEN_THIN_WIDTH)); * //Get выбранное значение  
    int nCurSel = pThinComboBox -> GetCurSel(); Если (nCurSel > = 0)  
{  
m_nThinWidth = atoi (pThinComboBox -> GetItem(nCurSel));

 } * / / Создание нового с помощью выбранной толщины пера  
    ReplacePen();

 ```  
  
7.  Next, create a menu item and event handlers for the thick pen.  
  
    1.  In the **Resource View** window, open the IDR_SCRIBBTYPE menu resource.  
  
    2.  Click **Pen** to open the pen menu. Then click **Type Here** and type *Thic&k Pen*.  
  
    3.  Right-click the text that you just typed to display the **Properties** window. Change the ID property to *ID_PEN_THICK_WIDTH*.  
  
    4.  Right-click the **Thick Pen** menu item that you just created and then click **Add Event Handler**. The **Event Handler Wizard** is displayed.  
  
    5.  In the **Class list** box of the wizard, select **CScribbleDoc** and then click **Add and Edit**. This creates an event handler named `CScribbleDoc::OnPenThickWidth`.  
  
    6.  Add the following code to `CScribbleDoc::OnPenThickWidth`.  
  
 ``` *// Get a pointer to the ribbon bar  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
    CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
*// Get the selected value  
    int nCurSel = pThickComboBox->GetCurSel();
if (nCurSel>= 0)  
 {  
    m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));

 } *// Create a new pen using the selected width  
    ReplacePen();

 ```  
  
8.  Сохранить изменения и затем постройте и запустите приложение. Отображать новые кнопки и поля со списком. Попробуйте использовать другой толщины для scribble.  
  
 [[Разделы](#top)]  
  
##  <a name="addcolorbutton"></a> Добавление кнопки цвет пера панели  
 Добавьте [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) объект, позволяющий пользователю scribble цветом.  
  
#### <a name="to-add-a-color-button-to-the-pen-panel"></a>Чтобы добавить кнопку цвета на панель «перо»  
  
1.  Прежде чем добавить кнопку цвета, создайте пункт меню для него. В **представление ресурсов** окно, открыть ресурс меню IDR_SCRIBBTYPE. Нажмите кнопку **перо** пункт меню, чтобы открыть меню «перо». Нажмите кнопку **введите здесь** и тип *& цвет*. Щелкните правой кнопкой мыши текст, указанный для отображения **свойства** окна. Измените идентификатор на *ID_PEN_COLOR*.  
  
2.  Теперь можно добавьте кнопку цвета. Из **элементов**, перетащите **кнопку цвета** для **перо** панель.  
  
3.  Нажмите кнопку цвета. Изменение **заголовок** для *цвет*, **идентификатор** для *ID_PEN_COLOR*, **SimpleLook** для  *Значение true,*, **индекс большого изображения** для *1*, и **режим разбиения** для *False*.  
  
4.  Сохранить изменения и затем постройте и запустите приложение. Должны отображаться на кнопке создания цвет **перо** панель. Однако он не может использоваться, поскольку он еще не обработчика событий. Следующие шаги демонстрируют добавить обработчик событий для кнопки «цвет».  
  
 [[Разделы](#top)]  
  
##  <a name="addcolormember"></a> Добавление члена цвет класс документа  
 Так как в исходном приложении Scribble не имеет цвет перья, для них необходимо написать реализацию. Чтобы сохранить цвет пера документа, Добавление нового элемента класс документа `CscribbleDoc.`  
  
#### <a name="to-add-a-color-member-to-the-document-class"></a>Для добавления члена цвет класс документа  
  
1.  В scribdoc.h в `CScribbleDoc` класса, найти `// Attributes` раздела. Добавьте следующий код после определения `m_nThickWidth` члена данных.  
  
 "" * / / Цвет пера текущего  
    COLORREF m_penColor;  
 ```  
  
2.  Every document contains a list of stokes that the user has already drawn. Every stroke is defined by a `CStroke` object. The `CStroke` class does not include information about pen color. Therefore, you must modify the class. In scribdoc.h, in the `CStroke` class, add the following lines of code after the definition of the `m_nPenWidth` data member.  
  
 ``` *// Pen color for the stroke  
    COLORREF m_penColor;  
 ```  
  
3.  В scribdoc.h, добавьте новый `CStroke` конструктор, параметры которого задайте ширину и цвет. Добавьте следующую строку кода после `CStroke(UINT nPenWidth);` инструкции.  
  
 ```  
    CStroke(UINT nPenWidth, COLORREF penColor);

 ```  
  
4.  В scribdoc.cpp, добавьте реализацию нового `CStroke` конструктор. Добавьте следующий код после реализации `CStroke::CStroke(UINT nPenWidth)` конструктор.  
  
 '' "* / / Конструктор, использующий документа текущей ширины и цвета  
    CStroke::CStroke (UINT nPenWidth, COLORREF penColor)  
 {  
    m_nPenWidth = nPenWidth;  
    m_penColor = penColor;  
    m_rectBounding.SetRectEmpty();

 }  
 ```  
  
5.  Change the second line of the `CStroke::DrawStroke` method as follows.  
  
 ```  
    Если (! penStroke.CreatePen (PS_SOLID m_nPenWidth, m_penColor))  
 ```  
  
6.  Set the default pen color for the document class. In scribdoc.cpp, add the following lines to `CScribbleDoc::InitDocument`, after the `m_nThickWidth = 5;` statement.  
  
 ``` *// default pen color is black  
    m_penColor = RGB(0,
    0,
    0);

 ```  
  
7.  В scribdoc.cpp, измените первой строки `CScribbleDoc::NewStroke` метод следующее.  
  
 ```  
    CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);

 ```  
  
8.  Изменения в последней строке `CScribbleDoc::ReplacePen` метод следующее.  
  
 ```  
    m_penCur.CreatePen(PS_SOLID,
    m_nPenWidth,
    m_penColor);

 ```  
  
9. Вы добавили `m_penColor` члена в предыдущем шаге. Теперь создайте обработчик событий для кнопки цвета, которая задает член.  
  
    1.  В **представление ресурсов** окно, открыть ресурс меню IDR_SCRIBBTYPE.  
  
    2.  Щелкните правой кнопкой мыши **цвет** пункт меню и нажмите кнопку **добавить обработчик событий**. **Мастер обработчиков событий** отображается.  
  
    3.  В **список классов** поле в мастере выберите **CScribbleDoc** и нажмите кнопку **добавлять и редактировать** кнопки. При этом создается `CScribbleDoc::OnPenColor` заглушки обработчик события.  
  
10. Замените заглушку для `CScribbleDoc::OnPenColor` обработчик событий следующим кодом.  
  
 ```  
    void CScribbleDoc::OnPenColor()  
 { *// Change pen color to reflect color button's current selection  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
    CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

    m_penColor = pColorBtn->GetColor();
*// Create new pen using the selected color  
    ReplacePen();

 }  
 ```  
  
11. Сохранить изменения и затем постройте и запустите приложение. Вы сможете нажмите кнопку цвета и изменить цвет пера.  
  
 [[Разделы](#top)]  
  
##  <a name="initpensave"></a> Инициализация перья и сохранение настроек  
 Затем инициализируйте цвет и ширину пера. Наконец сохранять и загружать цвет рисования из файла.  
  
#### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Для инициализации элементов управления на ленте  
  
1.  Инициализируйте перья на панели ленты.  
  
     Добавьте следующий код в scribdoc.cpp, `CScribbleDoc::InitDocument` метод после того, как `m_sizeDoc = CSize(200,200)` инструкции.  
  
 ``` *Сброс пользовательского интерфейса ленты для начального значения CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) -> GetRibbonBar(); ASSERT_VALID(pRibbon);

 CMFCRibbonColorButton * pColorBtn = DYNAMIC_DOWNCAST (CMFCRibbonColorButton, pRibbon -> FindByID(ID_PEN_COLOR)); * / / Set ColorButton черный  
    pColorBtn -> SetColor (RGB (0, 0, 0));

 CMFCRibbonComboBox * pThinComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox, pRibbon -> FindByID(ID_PEN_THIN_WIDTH)); * / / Set combobox тонкой перо 2  
    pThinComboBox -> SelectItem(1);

 CMFCRibbonComboBox * pThickComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox, pRibbon -> FindByID(ID_PEN_THICK_WIDTH)); * / / Set combobox толстой перо 5  
    pThickComboBox -> SelectItem(0);

 ```  
  
2.  Save a color drawing to a file. Add the following statement to scribdoc.cpp, in the `CStroke::Serialize` method, after the `ar << (WORD)m_nPenWidth;` statement.  
  
 ```  
    ar << m_penColor (COLORREF);  
 ```  
  
3.  Finally, load a color drawing from a file. Add the following line of code, in the `CStroke::Serialize` method, after the `m_nPenWidth = w;` statement.  
  
 ```  
    ar >> m_penColor;  
 ```  
  
4.  Now scribble in color and save your drawing to a file.  
  
 [[Sections](#top)]  
  
## Conclusion  
 You have updated the MFC Scribble application. Use this walkthrough as a guide when you modify your existing applications.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)   
 [Walkthrough: Updating the MFC Scribble Application (Part 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)

