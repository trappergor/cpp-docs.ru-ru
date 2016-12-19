---
title: "Пошаговое руководство. Добавление объекта D2D в проект MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D2D [MFC]"
  - "MFC - библиотека, D2D"
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
caps.latest.revision: 20
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пошаговое руководство. Добавление объекта D2D в проект MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом пошаговом руководстве рассматривается добавление базовых объектов Direct2D \(D2D\) в проект библиотеки Microsoft Foundation Class \(MFC\) на языке Visual C\+\+ и построение с помощью этого проекта приложения, которое выводит надпись "Hello, world" на фоне с градиентной заливкой.  
  
 В пошаговом руководстве показано, как выполнять следующие задачи:  
  
-   создание приложения MFC;  
  
-   создание кисти сплошного цвета и кисти линейного градиента;  
  
-   модификация кисти градиента, чтобы она изменялась в соответствии с изменением размера окна;  
  
-   реализация обработчика рисования D2D;  
  
-   проверка результатов.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## Обязательные компоненты  
 Для выполнения данного пошагового руководства требуется Visual Studio.  
  
### Создание приложения MFC  
  
1.  В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.  
  
2.  В левой области диалогового она **Новый проект** в разделе **Установленные шаблоны** разверните узел **Visual C\+\+** и выберите **MFC**.  В средней области выберите **Приложение MFC**.  В поле **Имя** введите `MFCD2DWalkthrough`.  Нажмите кнопку **ОК**.  
  
3.  В окне **Мастер приложений MFC** нажмите кнопку **Готово**, не изменяя никаких параметров.  
  
### Создание кисти сплошного цвета и кисти линейного градиента  
  
1.  В **Обозревателе решений** в проекте **MFCD2DWalkthrough** в папке **Заголовочные файлы** откройте файл MFCD2DWalkthroughView.h.  Добавьте в класс `CMFCD2DWalkthroughView` следующий код, чтобы создать три переменных с данными.  
  
    ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
    ```  
  
     Сохраните файл и закройте его.  
  
2.  В папке **Исходные файлы** откройте файл MFCD2DWalkthroughView.cpp.  В конструктор класса `CMFCD2DWalkthroughView` добавьте следующий код.  
  
    ```  
    // Enable D2D support for this window:  
    EnableD2DSupport();  
  
    // Initialize D2D resources:  
    m_pBlackBrush = new CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black));  
  
    m_pTextFormat = new CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);  
    m_pTextFormat->Get()->SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER);  
    m_pTextFormat->Get()->SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER);  
  
    D2D1_GRADIENT_STOP gradientStops[2];  
  
    gradientStops[0].color = D2D1::ColorF(D2D1::ColorF::White);  
    gradientStops[0].position = 0.f;  
    gradientStops[1].color = D2D1::ColorF(D2D1::ColorF::Indigo);  
    gradientStops[1].position = 1.f;  
  
    m_pLinearGradientBrush = new CD2DLinearGradientBrush(GetRenderTarget(),   
        gradientStops, ARRAYSIZE(gradientStops),  
        D2D1::LinearGradientBrushProperties(D2D1::Point2F(0, 0), D2D1::Point2F(0, 0)));  
    ```  
  
     Сохраните файл и закройте его.  
  
### Модификация кисти градиента, чтобы она изменялась в соответствии с изменением размера окна  
  
1.  В меню **Проект** выберите пункт **Мастер классов**.  
  
2.  В окне **Мастер классов MFC** в поле **Имя класса** выберите `CMFCD2DWalkthroughView`.  
  
3.  На вкладке **Сообщения** в поле **Сообщения** выберите `WM_SIZE` и щелкните **Добавить обработчик**.  Это действие добавит в класс `CMFCD2DWalkthroughView` обработчик сообщения `OnSize`.  
  
4.  В поле **Существующие обработчики** выберите `OnSize`.  Щелкните **Изменить код**, чтобы открыть метод `CMFCD2DWalkthroughView::OnSize`.  Добавьте следующий код в конец метода.  
  
    ```  
    m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));  
    ```  
  
     Сохраните файл и закройте его.  
  
### Реализация обработчика рисования D2D  
  
1.  В меню **Проект** выберите пункт **Мастер классов**.  
  
2.  В окне **Мастер классов MFC** в поле **Имя класса** выберите `CMFCD2DWalkthroughView`.  
  
3.  На вкладке **Сообщения** щелкните **Добавить настраиваемое сообщение**.  
  
4.  В диалоговом окне **Добавление настраиваемого сообщения** в поле **Настраиваемое сообщение Windows** введите `AFX_WM_DRAW2D`.  В поле **Имя обработчика сообщений** введите `OnDraw2D`.  Выберите параметр **Зарегистрированное сообщение** и нажмите кнопку **ОК**.  Это действие добавит в класс `CMFCD2DWalkthroughView` обработчик сообщения `AFX_WM_DRAW2D`.  
  
5.  В поле **Существующие обработчики** выберите `OnDraw2D`.  Щелкните **Изменить код**, чтобы открыть метод `CMFCD2DWalkthroughView::OnDraw2D`.  Воспользуйтесь следующим кодом для метода `CMFCD2DWalkthroughView::OnDrawD2D`.  
  
    ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
        CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;  
        ASSERT_VALID(pRenderTarget);  
  
        CRect rect;  
        GetClientRect(rect);  
  
        pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);  
        pRenderTarget->DrawText(_T("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);  
  
        return TRUE;  
    }  
    ```  
  
     Сохраните файл и закройте его.  
  
### Проверка результатов  
  
1.  Постройте и запустите приложение.  Должен появиться прямоугольник с градиентной заливкой, изменяющийся при изменении размера окна. В центре прямоугольника должна отображаться надпись "Hello World\!".  
  
## См. также  
 [Пошаговые руководства](../mfc/walkthroughs-mfc.md)