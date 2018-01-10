---
title: "Пошаговое руководство: Добавление анимации в проект MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f027da0e90bc8dde015c2d42bd72ceb388aa0bba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>Пошаговое руководство. Добавление анимации в проект MFC
Этом пошаговом руководстве рассматриваются способы добавления основные анимированного объекта Visual C++ проект библиотеки классов Microsoft Foundation (MFC).  
  
 Пошаговом руководстве показано, как выполнять следующие задачи:  
  
-   Создайте приложение MFC.  
  
-   Добавление меню и команд для запуска и остановки анимации.  
  
-   Создание обработчиков для команд запуска и остановки.  
  
-   Добавление анимированного объекта в проект.  
  
-   Центрирование анимированного объекта в окне.  
  
-   Проверка результатов.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства, необходимо иметь Visual Studio.  
  
### <a name="to-create-an-mfc-application"></a>Создание приложения MFC  
  
1.  В меню **Файл** выберите пункт **Создать** , а затем команду **Проект**.  
  
2.  В **новый проект** в левой области в разделе диалогового **установленные шаблоны**, разверните **Visual C++** , а затем выберите **MFC**. В средней области выберите **приложение MFC**. В поле **Имя** введите `MFCAnimationWalkthrough`. Нажмите кнопку **ОК**.  
  
3.  В **мастер приложений MFC** диалогового окна убедитесь, что **тип приложения** — **несколько документов**, **стиль проекта** —  **Visual Studio**и **поддержка архитектуры Document/View** выбран параметр. Нажмите кнопку **Готово**.  
  
### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Чтобы добавить меню и команд для запуска и остановки анимации  
  
1.  На **представление** последовательно выберите пункты **другие окна** и нажмите кнопку **представление ресурсов**.  
  
2.  В **представление ресурсов**, перейдите к **меню** папку и откройте его. Дважды щелкните `IDR_MFCAnimationWalTYPE` ресурс, чтобы открыть его для изменения.  
  
3.  В строке меню в **введите здесь** введите `A&nimation` для создания анимации меню.  
  
4.  В разделе **анимации**в **введите здесь** введите `Start &Forward` для создания команды запустить вперед.  
  
5.  В разделе **запустить вперед**в **введите здесь** введите `Start &Backward`.  
  
6.  В разделе **запустить Назад**в **введите здесь** введите `S&top` для создания команды остановки.  
  
7.  Сохраните MFCAnimationWalkthrough.rc и закройте его.  
  
8.  В **обозревателе решений**, дважды щелкните файл MainFrm.cpp, чтобы открыть его для изменения. В `CMainFrame::OnCreate` метод, найдите раздел, содержащий несколько вызовов `lstBasicCommands.AddTail`. Сразу после этого раздела добавьте следующий код.  
  
 ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);

 lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);

    lstBasicCommands.AddTail(ID_ANIMATION_STOP);

 ```  
  
9. Сохраните файл и закройте его.  
  
### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Для создания обработчиков для запуска и остановки команды  
  
1.  На **проекта** меню, нажмите кнопку **мастер классов**.  
  
2.  В **мастер классов MFC**в разделе **имя класса**выберите `CMFCAnimationWalkthroughView`.  
  
3.  На **команды** вкладку в **идентификаторы объектов** выберите `ID_ANIMATION_STARTFORWARD`, а затем в **сообщений** выберите `COMMAND`. Нажмите кнопку **добавить обработчик**.  
  
4.  В **Добавление функции-члена** диалоговое окно, нажмите кнопку **ОК**.  
  
5.  В **идентификаторы объектов** выберите `ID_ANIMATION_STARTBACKWARD`, а затем в **сообщений** выберите `COMMAND`. Нажмите кнопку **добавить обработчик**.  
  
6.  В **Добавление функции-члена** диалоговое окно, нажмите кнопку **ОК**.  
  
7.  В **идентификаторы объектов** выберите `ID_ANIMATION_STOP`, а затем в **сообщений** выберите `COMMAND`. Нажмите кнопку **добавить обработчик** и нажмите кнопку **ОК**.  
  
8.  В **Добавление функции-члена** диалоговое окно, нажмите кнопку **ОК**.  
  
9. В **мастер классов MFC**, нажмите кнопку **ОК**.  
  
10. Сохранить MFCAnimationWalkthroughView.cpp, который открыт в редакторе, однако не закрывать.  
  
### <a name="to-add-an-animated-object-to-the-project"></a>Добавление анимированного объекта в проект  
  
1.  В обозревателе решений дважды щелкните MFCAnimationWalkthroughView.h, чтобы открыть его для изменения. Непосредственно перед определением `CMFCAnimationWalkthroughView` добавьте следующий код, чтобы создать контроллер пользовательской анимации, который будет обрабатывать конфликты расписания объекта анимации.  
  
 ```  
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
  
2.  В конце `CMFCAnimationWalkthroughView` класса, добавьте следующий код.  
  
 ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
 ```  
  
3.  После `DECLARE_MESSAGE_MAP()` строка, добавьте следующий код.  
  
 ```  
    void Animate(BOOL bDirection);

 ```  
  
4.  Сохраните файл и закройте его.  
  
5.  В MFCAnimationWalkthroughView.cpp в верхней части файла после `#include` инструкций но прежде чем любом классе методы, добавьте следующий код.  
  
 ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
 ```  
  
6.  В конце конструктор `CMFCAnimationWalkthroughView`, добавьте следующий код.  
  
 ```  
    m_animationController.EnableAnimationTimerEventHandler();
m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);

 
    m_animationColor = RGB(255,
    255,
    255);

    m_animationRect = CRect(0,
    0,
    0,
    0);

 
    m_animationColor.SetID(-1,
    nAnimationGroup);

    m_animationRect.SetID(-1,
    nAnimationGroup);

 
    m_animationController.AddAnimationObject(&m_animationColor);

 m_animationController.AddAnimationObject(&m_animationRect);

 ```  
  
7.  Найдите `CAnimationWalthroughView::PreCreateWindow` метод и замените его следующим кодом.  
  
 ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
 { *// TODO: Modify the Window class or styles here by modifying *//  the CREATESTRUCT cs  
 
    m_animationController.SetRelatedWnd(this);

 return CView::PreCreateWindow(cs);

 }  
 ```  
  
8.  Найдите `CAnimationWalkthroughView::OnDraw` метод и замените его следующим кодом.  
  
 ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
 {  
    CMFCAnimationWalkthroughDoc* pDoc = GetDocument();
ASSERT_VALID(pDoc);

 if (!pDoc)  
    return; 
 *// TODO: add draw code for native data here  
    CMemDC dcMem(*pDC,
    this);

    CDC& dc = dcMem.GetDC();

 
    CRect rect;  
    GetClientRect(rect);

 
    dc.FillSolidRect(rect,
    GetSysColor(COLOR_WINDOW));

 
    CString strRGB;  
    strRGB.Format(_T("Fill Color is: %d; %d; %d"),
    GetRValue(m_animationColor),
    GetGValue(m_animationColor),
    GetBValue(m_animationColor));

 
    dc.DrawText(strRGB,
    rect,
    DT_CENTER);

    rect.top += nInfoAreaHeight;  
 
    CBrush br;  
 
    br.CreateSolidBrush(m_animationColor);

 CBrush* pBrushOld = dc.SelectObject(&br);

 
    dc.Rectangle((CRect)m_animationRect);

 dc.SelectObject(pBrushOld);

 }  
 ```  
  
9. В конце файла добавьте следующий код.  
  
 ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
 {  
    static UI_ANIMATION_SECONDS duration = 3;  
    static DOUBLE dblSpeed = 35.;  
    static BYTE nStartColor = 50;  
    static BYTE nEndColor = 255;  
 
    BYTE nRedColorFinal = bDirection  nStartColor : nEndColor;  
    BYTE nGreenColorFinal = bDirection  nStartColor : nEndColor;  
    BYTE nBlueColorFinal = bDirection  nStartColor : nEndColor;  
 
    CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

    CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

    CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

 
    m_animationColor.AddTransition(pRedTransition,
    pGreenTransition,
    pBlueTransition);

 
    CRect rectClient;  
    GetClientRect(rectClient);

 rectClient.top += nInfoAreaHeight;  
 
    int nLeftFinal = bDirection  rectClient.left : rectClient.CenterPoint().x;  
    int nTopFinal = bDirection  rectClient.top : rectClient.CenterPoint().y;  
    int nRightFinal = bDirection  rectClient.right : rectClient.CenterPoint().x;  
    int nBottomFinal = bDirection  rectClient.bottom : rectClient.CenterPoint().y;  
 
    CLinearTransition* pLeftTransition = new CLinearTransition(duration,
    nLeftFinal);

    CLinearTransition* pTopTransition = new CLinearTransition(duration,
    nTopFinal);

    CLinearTransition* pRightTransition = new CLinearTransition(duration,
    nRightFinal);

    CLinearTransition* pBottomTransition = new CLinearTransition(duration,
    nBottomFinal);

 
    m_animationRect.AddTransition(pLeftTransition,
    pTopTransition,
    pRightTransition,
    pBottomTransition);

 
    CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();
CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup,
    pBlueTransition);

 
    pLeftTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

    pTopTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

    pRightTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

    pBottomTransition->SetKeyframes(pKeyframeStart,
    pKeyFrameEnd);

 
    m_animationController.AnimateGroup(nAnimationGroup);

 }  
 ```  
  
10. На **проекта** меню, нажмите кнопку **мастер классов**.  
  
11. В **мастер классов MFC**в разделе **имя класса**выберите `CMFCAnimationWalkthroughView`.  
  
12. На **сообщений** вкладке **сообщений** выберите `WM_ERASEBKGND`, нажмите кнопку **добавить обработчик**и нажмите кнопку **ОК**.  
  
13. В MFCAnimationWalkthroughView.cpp, замените реализацию `OnEraseBkgnd` на следующий код, чтобы уменьшить отравляется анимированного объекта при его обновлении.  
  
 ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
 {  
    return TRUE;  
 }  
 ```  
  
14. Замените реализации `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward`, и `CMFCAnimationWalkthroughView::OnAnimationStop` следующим кодом.  
  
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
  
### <a name="to-center-the-animated-object-in-the-window"></a>Чтобы центрировать анимированного объекта в окне  
  
1.  В **обозревателе решений**, дважды щелкните MFCAnimationWalkthroughView.h, чтобы открыть его для изменения. В конце `CMFCAnimationWalkthroughView` класс сразу после определения `m_animationRect`, добавьте следующий код.  
  
 ```  
    BOOL m_bCurrentDirection;  
 ```  
  
2.  Сохраните файл и закройте его.  
  
3.  На **проекта** меню, нажмите кнопку **мастер классов**.  
  
4.  В **мастер классов MFC**в разделе **имя класса**выберите `CMFCAnimationWalkthroughView`.  
  
5.  На **сообщений** вкладке **сообщений** выберите `WM_SIZE`, нажмите кнопку **добавить обработчик**и нажмите кнопку **ОК**.  
  
6.  Замените код в MFCAnimationWalkthroughView.cpp, `CMFCAnimationWalkthroughView::OnSize` следующим кодом.  
  
 ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType,
    int cx,
    int cy)  
 {  
    CView::OnSize(nType,
    cx,
    cy);

 
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
  
7.  В начале конструктор `CMFCAnimationWalkthroughView`, добавьте следующий код.  
  
 ```  
    m_bCurrentDirection = TRUE;  
 ```  
  
8.  В начале `CMFCAnimationWalkthroughView::Animate` метод, добавьте следующий код.  
  
 ```  
    m_bCurrentDirection = bDirection;  
 ```  
  
9. Сохраните файл и закройте его.  
  
### <a name="to-verify-the-results"></a>Проверка результатов  
  
1.  Выполните сборку и запуск приложения. На **анимации** меню, нажмите кнопку **запустить вперед**. Прямоугольник должен отображаться, а затем заполнить центральную область. При нажатии кнопки **запустить Назад**, следует отменить анимации, а при нажатии кнопки **остановить**, его следует остановить. Следует изменить цвет заливки прямоугольника, в ходе выполнения анимации, а текущий цвет должен отображаться в верхней части окна анимации.  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства](../mfc/walkthroughs-mfc.md)

