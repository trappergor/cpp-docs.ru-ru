---
title: Пошаговое руководство. Обновление приложения MFC Scribble (часть 2)
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: bc204a152168accf3731eede8ca9ef960ab121d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360227"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>Пошаговое руководство. Обновление приложения MFC Scribble (часть 2)

[Часть 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) этого пошагового повествования показал, как добавить Office Fluent Ribbon в классическое приложение Scribble. В этой части показано, как добавлять ленточные панели и элементы управления, которые пользователи могут использовать вместо меню и команд.

## <a name="prerequisites"></a>Предварительные требования

[Примеры кода на Visual C++](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a>Разделы

Эта часть пошаговых отправления имеет следующие разделы:

- [Добавление новых панелей к ленте](#addnewpanel)

- [Добавление панели справки к ленте](#addhelppanel)

- [Добавление панели пера к ленте](#addpenpanel)

- [Добавление кнопки цвета к ленте](#addcolorbutton)

- [Добавление элемента цвета в класс документа](#addcolormember)

- [Инициализация ручек и сохранение предпочтений](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a>Добавление новых панелей к ленте

Эти шаги показывают, как добавить панель **View,** которая содержит два флажка, которые контролируют видимость панели инструментов и панели состояния, а также панель **Window,** которая содержит вертикально ориентированную кнопку сплита, которая управляет созданием и расположением многодокументных интерфейсов (MDI) окон.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>Добавление панели View и панели window в ленточном батончике

1. Создайте панель `View`с именем , которая имеет два флажка, которые переключают панель статуса и панель инструментов.

   1. Из **инструментария**перетащите **панель** в категорию **Home.** Затем перетащите два **чек-бокса** на панель.

   1. Нажмите на панель, чтобы изменить ее свойства. Изменение **Caption** подпись `View`к .

   1. Нажмите на первый флажок, чтобы изменить его свойства. Изменение **идентификатора** `ID_VIEW_TOOLBAR` и **подписи** к `Toolbar`.

   1. Нажмите на второй флажок, чтобы изменить его свойства. Изменение **идентификатора** `ID_VIEW_STATUS_BAR` и **подписи** к `Status Bar`.

1. Создайте панель `Window` с именем, которая имеет кнопку разделения. Когда пользователь нажимает кнопку сплита, меню ярлыка отображает три команды, которые уже определены в приложении Scribble.

   1. Из **инструментария**перетащите **панель** в категорию **Home.** Затем перетащите **кнопку** к панели.

   1. Нажмите на панель, чтобы изменить ее свойства. Изменение **Caption** подпись `Window`к .

   1. Нажмите кнопку. Изменение **Caption** подпись `Windows`к `w`, **Ключи** к `1`, **Большой индекс изображения,** и **сплит-режим** для `False`. Затем нажмите эллипсис **(...**) рядом с **пунктами меню,** чтобы открыть диалоговую коробку **редактора элементов.**

   1. Нажмите **Добавить** три раза, чтобы добавить три кнопки.

   1. Нажмите на первую кнопку, а `ID_WINDOW_NEW`затем изменить **подпись** к `New Window`, и **ID** .

   1. Нажмите вторую кнопку, `Cascade`а затем `ID_WINDOW_CASCADE`изменить **подпись** к , и **ID** .

   1. Нажмите на третью кнопку, а `ID_WINDOW_TILE_HORZ`затем изменить **подпись** к `Tile`, и **ID** .

1. Сохранить изменения, а затем построить и запустить приложение. Панели **представления** и **окна** должны отображаться. Нажмите на кнопки, чтобы подтвердить, что они функционируют правильно.

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a>Добавление панели справки к ленте

Теперь вы можете назначить два элемента меню, которые определены в приложении Scribble, к кнопкам ленты, которые **названы Help Topics** и **About Scribble.** Кнопки добавляются в новую панель под названием **Справка**.

### <a name="to-add-a-help-panel"></a>Добавление панели справки

1. Из **инструментария**перетащите **панель** в категорию **Home.** Затем перетащите две **кнопки** на панель.

1. Нажмите на панель, чтобы изменить ее свойства. Изменение **Caption** подпись `Help`к .

1. Нажмите на первую кнопку. Изменение **Caption** подпись `Help Topics`к , `ID_HELP_FINDER`и **ID** .

1. Нажмите вторую кнопку. Изменение **Caption** подпись `About Scribble...`к , `ID_APP_ABOUT`и **ID** .

1. Сохранить изменения, а затем построить и запустить приложение. Панель **справки,** содержащая две кнопки ленты, должна отображаться.

   > [!IMPORTANT]
   > При нажатии **кнопки «Темы справки»** приложение Scribble открывает сжатый файл справки HTML (.chm) под названием *your_project_name*.chm. Следовательно, если ваш проект не называется Scribble, вы должны переименовать файл справки в название проекта.

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a>Добавление панели пера к ленте

Теперь добавьте панель для отображения кнопок, которые контролируют толщину и цвет пера. Эта панель содержит флажок, который переключается между толстыми и тонкими ручками. Его функциональность напоминает элемент меню **Thick Line** в приложении Scribble.

Оригинальное приложение Scribble позволяет пользователю выбирать ширину пера из диалогового окна, которое появляется при нажатии **на ширину пера** в меню. Поскольку лента бар имеет достаточно места для новых элементов управления, вы можете заменить диалог овсянку с помощью двух комбо-коробок на ленте. Одна комбо-коробка регулирует ширину тонкого пера, а другая комбо-коробка регулирует ширину толстой ручки.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>Чтобы добавить панель пера и комбо коробки на ленту

1. Из **инструментария**перетащите **панель** в категорию **Home.** Затем перетащите **Check Box** и два **Комбо коробки** на панели.

1. Нажмите на панель, чтобы изменить ее свойства. Изменение **Caption** подпись `Pen`к .

1. Установите флажок. Изменение **Caption** подпись `Use Thick`к , `ID_PEN_THICK_OR_THIN`и **ID** .

1. Нажмите на первую комбо-коробку. Изменение **подписи** `Thin Pen`к, **ID** к, `1;2;3;4;5;6;7;8;9;` `ID_PEN_THIN_WIDTH` **Введите** к, `Drop List` **Данные** к, и **Текст** к `2`.

1. Нажмите на вторую комбо-коробку. Изменение **подписи** `Thick Pen`к, **ID** к, `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;` `ID_PEN_THICK_WIDTH` **Введите** к, `Drop List` **Данные** к, и **Текст** к `5`.

1. Новые комбо-коробки не соответствуют существующим пунктам меню, поэтому необходимо создать пункт меню для каждого варианта пера.

   1. В окне **просмотра ресурсов** откройте ресурс **меню IDR_SCRIBBTYPE.**

   1. Нажмите **перо,** чтобы открыть меню пера. Затем нажмите Тип `Thi&n Pen` **Здесь** и введите .

   1. Нажмите на текст, который вы набрали, чтобы открыть окно `ID_PEN_THIN_WIDTH` **Свойств,** а затем измените свойство идентификатора на .

   1. Создайте обработчик событий для каждого элемента меню пера. Нажмите правой кнопкой мыши на пункт меню **Thi&n Pen,** который вы создали, а затем нажмите **Добавить обработчик событий.** **Отображается Мастер обработчика событий.**

   1. В поле **списка класса** в мастере выберите **CScribbleDoc,** а затем нажмите **Добавить и отсватить.** Команда создает обработчик `CScribbleDoc::OnPenThinWidth`событий под названием .

   1. Добавьте следующий код к `CScribbleDoc::OnPenThinWidth`.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        // Get a pointer to the Thin Width combo box
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
        CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

        //Get the selected value
        int nCurSel = pThinComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Затем создайте элемент меню и обработчики событий для толстой ручки.

   1. В окне **просмотра ресурсов** откройте ресурс **меню IDR_SCRIBBTYPE.**

   1. Нажмите **перо,** чтобы открыть меню пера. Затем нажмите Тип `Thic&k Pen` **Здесь** и введите .

   1. Нажмите справа на текст, который вы набрали для отображения окна **Свойств.** Измените свойство `ID_PEN_THICK_WIDTH`идентификатора на .

   1. Нажмите правой кнопкой кнопку **Thick Pen** пункт меню, которое вы создали, а затем нажмите **Добавить обработчик события**. **Отображается Мастер обработчика событий.**

   1. В поле **списка класса** мастера выберите **CScribbleDoc,** а затем нажмите **Добавить и отсватить.** Команда создает обработчик `CScribbleDoc::OnPenThickWidth`событий под названием .

   1. Добавьте следующий код к `CScribbleDoc::OnPenThickWidth`.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
            CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
        // Get the selected value
        int nCurSel = pThickComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. Сохранить изменения, а затем построить и запустить приложение. Новые кнопки и комбо коробки должны быть отображены. Попробуйте использовать различные ширины пера, чтобы каракули.

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a>Добавление кнопки цвета к панели пера

Затем добавьте объект [CMFCRibbonColorButton,](../mfc/reference/cmfcribboncolorbutton-class.md) который позволяет пользователю каракули в цвете.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>Добавление кнопки цвета к панели pen

1. Перед добавлением кнопки «Цвет» создайте для нее элемент меню. В окне **просмотра ресурсов** откройте ресурс **меню IDR_SCRIBBTYPE.** Нажмите на пункт меню **Pen,** чтобы открыть меню пера. Затем нажмите Тип `&Color` **Здесь** и введите . Нажмите справа на текст, который вы набрали для отображения окна **Свойств.** Измените идентификатор на `ID_PEN_COLOR`.

1. Теперь добавьте кнопку цвета. Из **toolbox**перетащите **кнопку цвета** к панели **pen.**

1. Нажмите кнопку цвета. Изменение **Caption** подпись `Color`к, `ID_PEN_COLOR` **ID** к `True`, **Простой взгляд** на , **Большой индекс** `1`изображения, и **сплит режим** . `False`

1. Сохранить изменения, а затем построить и запустить приложение. Новая цветная кнопка должна отображаться на панели **pen.** Тем не менее, он не может быть использован, поскольку он еще не имеет обработчик анонса событий. Следующие шаги показывают, как добавить обработчик событий для кнопки цвета.

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a>Добавление элемента цвета в класс документа

Поскольку в исходном приложении Scribble нет цветных ручек, необходимо написать для них реализацию. Чтобы сохранить цвет пера документа, добавьте нового участника `CscribbleDoc`в класс документа.

### <a name="to-add-a-color-member-to-the-document-class"></a>Добавление элемента цвета в класс документа

1. В scribdoc.h, `CScribbleDoc` в классе, `// Attributes` найти раздел. Добавьте следующие строки кода `m_nThickWidth` после определения члена данных.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. Каждый документ содержит список топит, что пользователь уже обращается. Каждый штрих определяется объектом. `CStroke` Класс `CStroke` не содержит информацию о цвете пера, поэтому необходимо изменить класс. В scribdoc.h в `CStroke` классе добавьте следующие строки кода `m_nPenWidth` после определения члена данных.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. В scribdoc.h добавьте `CStroke` новый конструктор, параметры которого указывают ширину и цвет. Добавьте следующую строку `CStroke(UINT nPenWidth);` кода после оператора.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. В scribdoc.cpp добавьте реализацию `CStroke` нового конструктора. Добавьте следующий код после `CStroke::CStroke(UINT nPenWidth)` реализации конструктора.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. Измените вторую `CStroke::DrawStroke` строку метода следующим образом.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. Установите цвет пера по умолчанию для класса документа. В scribdoc.cpp, добавить `CScribbleDoc::InitDocument`следующие `m_nThickWidth = 5;` строки, после заявления.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. В scribdoc.cpp измените первую `CScribbleDoc::NewStroke` строку метода на следующую.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. Измените последнюю `CScribbleDoc::ReplacePen` строку метода на следующую.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. Вы добавили `m_penColor` участника на предыдущем этапе. Создайте обработчик событий для кнопки цвета, которая устанавливает элемент.

   1. В окне **просмотра ресурсов** откройте ресурс меню IDR_SCRIBBTYPE.

   1. Нажмите правой кнопкой мыши элемент меню **цвета** и нажмите **Добавить обработчик события**. **Появляется мастер обработчик событий.**

   1. В поле **списка класса** в мастере выберите **CScribbleDoc,** а затем нажмите кнопку **Добавить и отменить.** Команда создает `CScribbleDoc::OnPenColor` заглушку обработчика событий.

1. Замените заглушку обработчика `CScribbleDoc::OnPenColor` событий следующим кодом.

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

1. Сохранить изменения, а затем построить и запустить приложение. Теперь вы можете нажать кнопку цвета и изменить цвет пера.

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a>Инициализация ручек и сохранение предпочтений

Далее, инициализируем цвет и ширину ручек. Наконец, сохраните и загрузите цветной рисунок из файла.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>Инициализация элементов управления на ленте бар

1. Инициализируем ручки на ленте.

   Добавьте следующий код в scribdoc.cpp в `m_sizeDoc = CSize(200,200)` методе `CScribbleDoc::InitDocument` после оператора.

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

1. Сохранить цветной рисунок в файле. Добавьте следующее утверждение на scribdoc.cpp в `ar << (WORD)m_nPenWidth;` методе `CStroke::Serialize` после оператора.

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. Наконец, загрузите цветной рисунок из файла. Добавьте следующую строку `CStroke::Serialize` кода в `m_nPenWidth = w;` метод после оператора.

   ```cpp
   ar >> m_penColor;
   ```

1. Теперь каракули в цвете и сохранить рисунок в файл.

## <a name="conclusion"></a>Заключение

Вы обновили приложение MFC Scribble. Используйте это пошаговое руководство при изменении существующих приложений.

## <a name="see-also"></a>См. также раздел

[Пошаговые руководства](../mfc/walkthroughs-mfc.md)<br/>
[Пошаговое руководство. Обновление приложения MFC Scribble (часть 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
