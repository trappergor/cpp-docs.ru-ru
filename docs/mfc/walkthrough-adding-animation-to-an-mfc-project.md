---
title: 'Пошаговое руководство: Добавление анимации в проект MFC | Документация Майкрософт'
ms.custom: ''
ms.date: 09/20/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 326535395599a76f521100475cfc80b014ba6cd9
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169441"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>Пошаговое руководство. Добавление анимации в проект MFC

В этом пошаговом руководстве объясняется, как добавить базовый анимированный объект в Visual C++, проект Microsoft Foundation Class Library (MFC).

Пошаговом руководстве показано, как выполнять следующие задачи:

- Создайте приложение MFC.

- Добавление меню и команд для запуска и остановки анимации.

- Создание обработчиков для команд запуска и остановки.

- Добавьте в проект анимированный объект.

- Центр анимированный объект в окне.

- Проверьте результаты.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства, необходимо иметь Visual Studio.

### <a name="to-create-an-mfc-application"></a>Создание приложения MFC

1. В меню **Файл** выберите пункт **Создать** , а затем команду **Проект**.

1. В **новый проект** диалоговое окно, в области слева в разделе **установленные шаблоны**, разверните **Visual C++** , а затем выберите **MFC**. В средней области выберите **приложения MFC**. В **имя** введите *MFCAnimationWalkthrough*. Нажмите кнопку **ОК**.

1. В **мастер приложений MFC** диалогового окна убедитесь, что **тип приложения** — **несколько документов**, **стиль проекта** является  **Visual Studio**и **поддержка архитектуры Document/View** выбран параметр. Нажмите кнопку **Готово**.

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Чтобы добавить меню и команд для запуска и остановки анимации

1. На **представление** последовательно выберите пункты **Other Windows** и нажмите кнопку **представление ресурсов**.

1. В **представление ресурсов**, перейдите к **меню** папку и откройте его. Дважды щелкните **IDR_MFCAnimationWalkthroughTYPE** ресурс, чтобы открыть его для изменения.

1. В строке меню в **введите здесь** введите *& анимация* для создания анимации меню.

1. В разделе **анимации**в **введите здесь** введите *запустить & вперед* для создания команды запустить вперед.

1. В разделе **запустить вперед**в **введите здесь** введите *запустить & назад*.

1. В разделе **запустить Назад**в **введите здесь** введите *ОС & тановить* для создания команды остановки.

1. Сохраните MFCAnimationWalkthrough.rc и закройте его.

1. В **обозревателе решений**, дважды щелкните файл MainFrm.cpp, чтобы открыть его для изменения. В `CMainFrame::OnCreate` метод, найдите раздел, содержащий несколько вызовов `lstBasicCommands.AddTail`. Сразу после этого раздела добавьте следующий код.

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

1. Сохраните файл и закройте его.

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Для создания обработчиков для начала и остановки команды

1. На **проекта** меню, щелкните **мастер классов**.

1. В **мастер классов MFC**в разделе **имя класса**выберите **CMFCAnimationWalkthroughView**.

1. На **команды** на вкладке **идентификаторы объектов** выберите **ID_ANIMATION_STARTFORWARD**, а затем в **сообщений** выберите  **КОМАНДА**. Нажмите кнопку **добавьте обработчик**.

1. В **добавить функцию-член** диалоговом окне щелкните **ОК**.

1. В **идентификаторы объектов** выберите **ID_ANIMATION_STARTBACKWARD**, а затем в **сообщений** выберите **команда**. Нажмите кнопку **добавьте обработчик**.

1. В **добавить функцию-член** диалоговом окне щелкните **ОК**.

1. В **идентификаторы объектов** выберите **ID_ANIMATION_STOP**, а затем в **сообщений** выберите **команда**. Нажмите кнопку **добавить обработчик** и нажмите кнопку **ОК**.

1. В **добавить функцию-член** диалоговом окне щелкните **ОК**.

1. В **мастер классов MFC**, нажмите кнопку **ОК**.

1. Сохранить MFCAnimationWalkthroughView.cpp, который открыт в редакторе, но не закрывайте его.

### <a name="to-add-an-animated-object-to-the-project"></a>Чтобы добавить анимированного объекта в проект

1. В обозревателе решений дважды щелкните MFCAnimationWalkthroughView.h, чтобы открыть его для изменения. Непосредственно перед определение `CMFCAnimationWalkthroughView` класса, добавьте следующий код для создания пользовательской анимации контроллер, который будет обрабатывать конфликты расписания объекта анимации.

    ```cpp
    class CCustomAnimationController : public CAnimationController
    {
    public:
        CCustomAnimationController()
        {
        }

        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled,
            CAnimationGroup* pGroupNew,
            UI_ANIMATION_PRIORITY_EFFECT priorityEffect)
        {
            return TRUE;
        }
    };
    ```

1. В конце `CMFCAnimationWalkthroughView` класса, добавьте следующий код.

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

1. После `DECLARE_MESSAGE_MAP()` строка, добавьте следующий код.

    ```cpp
    void Animate(BOOL bDirection);
    ```

1. Сохраните файл и закройте его.

1. В MFCAnimationWalkthroughView.cpp, в верхней части файла после `#include` инструкций но прежде чем в любом классе методы, добавьте следующий код.

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

1. В конце конструктор `CMFCAnimationWalkthroughView`, добавьте следующий код.

    ```cpp
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);
    m_animationColor = RGB(255, 255, 255);
    m_animationRect = CRect(0, 0, 0, 0);
    m_animationColor.SetID(-1, nAnimationGroup);
    m_animationRect.SetID(-1, nAnimationGroup);
    m_animationController.AddAnimationObject(&m_animationColor);
    m_animationController.AddAnimationObject(&m_animationRect);
    ```

1. Найдите `CAnimationWalthroughView::PreCreateWindow` метод и замените его следующим кодом.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

1. Найдите `CAnimationWalkthroughView::OnDraw` метод и замените его следующим кодом.

    ```cpp
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
        strRGB.Format(_T("Fill Color is: %d; %d; %d"),
            GetRValue(m_animationColor),
            GetGValue(m_animationColor),
            GetBValue(m_animationColor));

        dc.DrawText(strRGB, rect, DT_CENTER);
        rect.top += nInfoAreaHeight;

        CBrush br;
        br.CreateSolidBrush(m_animationColor);
        CBrush* pBrushOld = dc.SelectObject(&br);

        dc.Rectangle((CRect)m_animationRect);

        dc.SelectObject(pBrushOld);
    }
    ```

1. В конце файла добавьте следующий код.

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;

        CLinearTransition* pRedTransition =
            new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

        CSmoothStopTransition* pGreenTransition =
            new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

        CLinearTransitionFromSpeed* pBlueTransition =
            new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

        m_animationColor.AddTransition(pRedTransition,
            pGreenTransition,
            pBlueTransition);

        CRect rectClient;
        GetClientRect(rectClient);

        rectClient.top += nInfoAreaHeight;

        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;

        CLinearTransition* pLeftTransition =
            new CLinearTransition(duration, nLeftFinal);

        CLinearTransition* pTopTransition =
            new CLinearTransition(duration, nTopFinal);

        CLinearTransition* pRightTransition =
            new CLinearTransition(duration, nRightFinal);

        CLinearTransition* pBottomTransition =
            new CLinearTransition(duration, nBottomFinal);

        m_animationRect.AddTransition(pLeftTransition,
            pTopTransition,
            pRightTransition,
            pBottomTransition);

        CBaseKeyFrame* pKeyframeStart =
            CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd =
            m_animationController.CreateKeyframe(nAnimationGroup,
                pBlueTransition);

        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);

        m_animationController.AnimateGroup(nAnimationGroup);
    }
    ```

1. На **проекта** меню, щелкните **мастер классов**.

1. В **мастер классов MFC**в разделе **имя класса**выберите **CMFCAnimationWalkthroughView**.

1. На **сообщений** на вкладке **сообщений** выберите **WM_ERASEBKGND**, нажмите кнопку **добавить обработчик**, а затем нажмите кнопку **ОК** .

1. В MFCAnimationWalkthroughView.cpp, замените реализацию `OnEraseBkgnd` следующим кодом, чтобы снизить мерцание в анимированный объект при его обновлении.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

1. Замените реализации `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward`, и `CMFCAnimationWalkthroughView::OnAnimationStop` следующим кодом.

    ```cpp
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

1. Сохраните файл и закройте его.

### <a name="to-center-the-animated-object-in-the-window"></a>Чтобы центрировать анимированный объект в окне

1. В **обозревателе решений**, дважды щелкните MFCAnimationWalkthroughView.h, чтобы открыть его для изменения. В конце `CMFCAnimationWalkthroughView` класс, сразу после определения `m_animationRect`, добавьте следующий код.

    ```cpp
    BOOL m_bCurrentDirection;
    ```

1. Сохраните файл и закройте его.

1. На **проекта** меню, щелкните **мастер классов**.

1. В **мастер классов MFC**в разделе **имя класса**выберите **CMFCAnimationWalkthroughView**.

1. На **сообщений** на вкладке **сообщений** выберите **WM_SIZE**, нажмите кнопку **добавить обработчик**, а затем нажмите кнопку **ОК**.

1. В MFCAnimationWalkthroughView.cpp, замените код `CMFCAnimationWalkthroughView::OnSize` следующим кодом.

    ```cpp
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

1. В начале конструктор `CMFCAnimationWalkthroughView`, добавьте следующий код.

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

1. В начале `CMFCAnimationWalkthroughView::Animate` метод, добавьте следующий код.

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

1. Сохраните файл и закройте его.

### <a name="to-verify-the-results"></a>Проверка результатов

1. Выполните сборку и запуск приложения. На **анимации** меню, щелкните **запустить вперед**. Прямоугольник должен отображаться, а затем укажите центральную область. При нажатии кнопки **запустить Назад**, следует отменить анимации, а при нажатии кнопки **остановить**, его следует остановить. Цвет заливки прямоугольника следует изменить в ходе выполнения анимации и текущего цвета, которые должны отображаться в верхней части окна анимации.

## <a name="see-also"></a>См. также

[Пошаговые руководства](../mfc/walkthroughs-mfc.md)
