---
title: "Пошаговое руководство. Добавление анимации в проект MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "анимация [MFC]"
  - "MFC - библиотека, анимация"
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Пошаговое руководство. Добавление анимации в проект MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом пошаговом руководстве показано, как добавить простой анимированный объект в проект библиотеки Microsoft Foundation Class \(MFC\) на языке Visual C\+\+.  
  
 В пошаговом руководстве показано, как выполнять следующие задачи:  
  
-   создание приложения MFC;  
  
-   добавление меню и команд для запуска и остановки анимации;  
  
-   создание обработчиков для команд запуска и остановки;  
  
-   добавление анимированного объекта в проект;  
  
-   центрирование анимированного объекта в окне;  
  
-   проверка результатов.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## Обязательные компоненты  
 Для выполнения данного пошагового руководства требуется Visual Studio.  
  
### Создание приложения MFC  
  
1.  В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.  
  
2.  В левой области диалогового она **Новый проект** в разделе **Установленные шаблоны** разверните узел **Visual C\+\+** и выберите **MFC**.  В средней области выберите **Приложение MFC**.  В поле **Имя** введите `MFCAnimationWalkthrough`.  Нажмите кнопку **ОК**.  
  
3.  В диалоговом окне **Мастер приложений MFC** проверьте, что поле **Тип приложения** имеет значение **Многооконный**, поле **Стиль проекта** — значение **Visual Studio** и что выбран параметр **Поддержка архитектуры Document\/View**.  Нажмите кнопку **Готово**.  
  
### Добавление меню и команд для запуска и остановки анимации  
  
1.  В меню **Вид** выберите команду **Другие окна** и щелкните **Представление ресурсов**.  
  
2.  В окне **Представление ресурсов** перейдите к папке **Меню** и откройте ее.  Дважды щелкните ресурс `IDR_MFCAnimationWalTYPE`, чтобы открыть его для изменения.  
  
3.  В строке меню в поле **Прототип для текста** введите `A&nimation`, чтобы создать меню анимации.  
  
4.  В разделе **Анимация** в поле **Прототип для текста** введите `Запуск &Вперед`, чтобы создать команду " вперед.  
  
5.  В разделе **Поиск "** в поле **Прототип для текста** введите `Запуск &Назад`.  
  
6.  В разделе **Запустите назад** в поле **Прототип для текста** введите `S&верх`, чтобы создать команду остановки.  
  
7.  Сохраните файл MFCAnimationWalkthrough.rc и закройте его.  
  
8.  В окне **Обозреватель решений** дважды щелкните файл MainFrm.cpp, чтобы открыть его для изменения.  В методе `CMainFrame::OnCreate` найдите раздел, содержащий несколько вызовов `lstBasicCommands.AddTail`.  Сразу после этого раздела вставьте следующий код.  
  
    ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);  
    ```  
  
9. Сохраните файл и закройте его.  
  
### Создание обработчиков для команд запуска и остановки  
  
1.  В меню **Проект** выберите пункт **Мастер классов**.  
  
2.  В окне **Мастер классов MFC** в поле **Имя класса** выберите `CMFCAnimationWalkthroughView`.  
  
3.  На вкладке **Команды** в поле **Идентификаторы объектов** выберите `ID_ANIMATION_STARTFORWARD`, после чего в поле **Сообщения** выберите `COMMAND`.  Щелкните **Добавить обработчик**.  
  
4.  В диалоговом окне **Добавление функции\-члена** нажмите кнопку **ОК**.  
  
5.  В поле **Идентификаторы объектов** выберите `ID_ANIMATION_STARTBACKWARD`, после чего в поле **Сообщения** выберите `COMMAND`.  Щелкните **Добавить обработчик**.  
  
6.  В диалоговом окне **Добавление функции\-члена** нажмите кнопку **ОК**.  
  
7.  В поле **Идентификаторы объектов** выберите `ID_ANIMATION_STOP`, после чего в поле **Сообщения** выберите `COMMAND`.  Щелкните **Добавить обработчик** и нажмите кнопку **ОК**.  
  
8.  В диалоговом окне **Добавление функции\-члена** нажмите кнопку **ОК**.  
  
9. В окне **Мастер классов MFC** нажмите кнопку **ОК**.  
  
10. Сохраните файл MFCAnimationWalkthroughView.cpp, открытый в редакторе, но не закрывайте его.  
  
### Добавление анимированного объекта в проект  
  
1.  В обозревателе решений дважды щелкните файл MFCAnimationWalkthroughView.h, чтобы открыть его для изменения.  Непосредственно перед определением класса `CMFCAnimationWalkthroughView` добавьте следующий код, создающий пользовательский контроллер анимации, который будет обрабатывать конфликты расписания объекта анимации.  
  
    ```  
    class CCustomAnimationController : public CAnimationController  
    {  
    public:  
        CCustomAnimationController()  
        {  
        }  
  
        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled, CAnimationGroup* pGroupNew, UI_ANIMATION_PRIORITY_EFFECT priorityEffect)  
        {  
            return TRUE;  
        }  
    };  
    ```  
  
2.  В конец класса `CMFCAnimationWalkthroughView` добавьте следующий код.  
  
    ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
    ```  
  
3.  После строки `DECLARE_MESSAGE_MAP()` добавьте следующий код.  
  
    ```  
    void Animate(BOOL bDirection);  
    ```  
  
4.  Сохраните файл и закройте его.  
  
5.  В верхней части файла MFCAnimationWalkthroughView.cpp после инструкций `#include`, но до методов класса, добавьте следующий код.  
  
    ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
    ```  
  
6.  В конце конструктора `CMFCAnimationWalkthroughView` добавьте следующий код.  
  
    ```  
    m_animationController.EnableAnimationTimerEventHandler();  
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);  
  
    m_animationColor = RGB(255, 255, 255);  
    m_animationRect = CRect(0, 0, 0, 0);  
  
    m_animationColor.SetID(-1, nAnimationGroup);  
    m_animationRect.SetID(-1, nAnimationGroup);  
  
    m_animationController.AddAnimationObject(&m_animationColor);  
    m_animationController.AddAnimationObject(&m_animationRect);  
    ```  
  
7.  Найдите метод `CAnimationWalthroughView::PreCreateWindow` и замените его следующим кодом.  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
    {  
        // TODO: Modify the Window class or styles here by modifying  
        //  the CREATESTRUCT cs  
  
        m_animationController.SetRelatedWnd(this);  
        return CView::PreCreateWindow(cs);  
    }  
    ```  
  
8.  Найдите метод `CAnimationWalkthroughView::OnDraw` и замените его следующим кодом.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
    {  
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();  
        ASSERT_VALID(pDoc);  
        if (!pDoc)  
            return;  
  
        // TODO: add draw code for native data here  
        CMemDC dcMem(*pDC, this);  
        CDC& dc = dcMem.GetDC();  
  
        CRect rect;  
        GetClientRect(rect);  
  
        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));  
  
        CString strRGB;  
        strRGB.Format(_T("Fill Color is: %d; %d; %d"), GetRValue(m_animationColor), GetGValue(m_animationColor), GetBValue(m_animationColor));  
  
        dc.DrawText(strRGB, rect, DT_CENTER);  
        rect.top += nInfoAreaHeight;  
  
        CBrush br;  
  
        br.CreateSolidBrush(m_animationColor);  
        CBrush* pBrushOld = dc.SelectObject(&br);  
  
        dc.Rectangle((CRect)m_animationRect);  
        dc.SelectObject(pBrushOld);  
    }  
    ```  
  
9. В конец файла добавьте следующий код.  
  
    ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
    {  
        static UI_ANIMATION_SECONDS duration = 3;  
        static DOUBLE dblSpeed = 35.;  
        static BYTE nStartColor = 50;  
        static BYTE nEndColor = 255;  
  
        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;  
  
        CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);  
        CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);  
        CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);  
  
        m_animationColor.AddTransition(pRedTransition, pGreenTransition, pBlueTransition);  
  
        CRect rectClient;  
        GetClientRect(rectClient);  
        rectClient.top += nInfoAreaHeight;  
  
        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;  
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;  
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;  
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;  
  
        CLinearTransition* pLeftTransition = new CLinearTransition(duration, nLeftFinal);  
        CLinearTransition* pTopTransition = new CLinearTransition(duration, nTopFinal);  
        CLinearTransition* pRightTransition = new CLinearTransition(duration, nRightFinal);  
        CLinearTransition* pBottomTransition = new CLinearTransition(duration, nBottomFinal);  
  
        m_animationRect.AddTransition(pLeftTransition, pTopTransition, pRightTransition, pBottomTransition);  
  
        CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();  
        CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup, pBlueTransition);  
  
        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
  
        m_animationController.AnimateGroup(nAnimationGroup);  
    }  
    ```  
  
10. В меню **Проект** выберите пункт **Мастер классов**.  
  
11. В окне **Мастер классов MFC** в поле **Имя класса** выберите `CMFCAnimationWalkthroughView`.  
  
12. На вкладке **Сообщения** в поле **Сообщения** выберите `WM_ERASEBKGND`, щелкните **Добавить обработчик** и нажмите кнопку **ОК**.  
  
13. В файле MFCAnimationWalkthroughView.cpp замените реализацию `OnEraseBkgnd` следующим кодом, чтобы ограничить мерцание анимированного объекта при его перерисовке.  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
    {  
        return TRUE;  
    }  
    ```  
  
14. Замените реализации `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward` и `CMFCAnimationWalkthroughView::OnAnimationStop` следующим кодом.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()  
    {  
        Animate(TRUE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()  
    {  
        Animate(FALSE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStop()  
    {  
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();  
        if (pManager != NULL)  
        {  
            pManager->AbandonAllStoryboards();  
        }  
    }  
  
    ```  
  
15. Сохраните файл и закройте его.  
  
### Центрирование анимированного объекта в окне  
  
1.  В **Обозревателе решений** дважды щелкните файл MFCAnimationWalkthroughView.h, чтобы открыть его для изменения.  В конец класса `CMFCAnimationWalkthroughView` сразу после определения `m_animationRect` добавьте следующий код.  
  
    ```  
    BOOL m_bCurrentDirection;  
    ```  
  
2.  Сохраните файл и закройте его.  
  
3.  В меню **Проект** выберите пункт **Мастер классов**.  
  
4.  В окне **Мастер классов MFC** в поле **Имя класса** выберите `CMFCAnimationWalkthroughView`.  
  
5.  На вкладке **Сообщения** в поле **Сообщения** выберите `WM_SIZE`, щелкните **Добавить обработчик** и нажмите кнопку **ОК**.  
  
6.  В файле MFCAnimationWalkthroughView.cpp замените код `CMFCAnimationWalkthroughView::OnSize` следующим кодом.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
  
        CRect rect;  
        GetClientRect(rect);  
        rect.top += nInfoAreaHeight;  
  
        CRect rectAnim = m_animationRect;  
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,   
                                rect.CenterPoint().y - rectAnim.Height() / 2),   
                                rectAnim.Size());  
  
        if (m_animationController.IsAnimationInProgress())  
        {  
            Animate(m_bCurrentDirection);  
        }  
    }  
    ```  
  
7.  В начале конструктора `CMFCAnimationWalkthroughView` добавьте следующий код.  
  
    ```  
    m_bCurrentDirection = TRUE;  
    ```  
  
8.  В начале метода `CMFCAnimationWalkthroughView::Animate` добавьте следующий код.  
  
    ```  
    m_bCurrentDirection = bDirection;  
    ```  
  
9. Сохраните файл и закройте его.  
  
### Проверка результатов  
  
1.  Постройте и запустите приложение.  В меню **Анимация** щелкните **Запустить вперед**.  Должен появиться прямоугольник, заполняющий центральную область.  При выборе команды **Запустить назад** анимация должна воспроизводиться в обратном направлении, а при выборе команды **Остановить** она должна остановиться.  Цвет заливки прямоугольника должен изменяться в процессе воспроизведения анимации, а текущий цвет должен отображаться в верхней части окна анимации.  
  
## См. также  
 [Пошаговые руководства](../mfc/walkthroughs-mfc.md)