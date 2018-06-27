---
title: 'Пошаговое руководство: Добавление объекта D2D в проект MFC | Документы Microsoft'
ms.custom: ''
ms.date: 06/19/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87e1c696f3da374d7b71e1b24e3a8bd3ebfe41b9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954875"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>Пошаговое руководство. Добавление объекта D2D в проект MFC

Этом пошаговом руководстве рассматриваются способы добавления основные Direct2D (D2D) объекта в Visual C++ проект библиотеки классов Microsoft Foundation (MFC) и затем постройте проект в приложение, которое выводит «Hello, world» на градиента фона.

Пошаговом руководстве показано, как выполнять следующие задачи:

- Создайте приложение MFC.

- Создайте кисть сплошного цвета и кисти линейного градиента.

- Измените градиентной кисти, чтобы она изменялась в соответствии с изменением размера окна.

- Реализация обработчика рисования D2D.

- Проверка результатов.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Предварительные требования

Для выполнения данного пошагового руководства, необходимо иметь устанавливается вместе с Visual Studio **разработки настольных приложений с помощью C++** рабочей нагрузки и необязательные **Visual C++ MFC для x86- и x64** компонента.

## <a name="to-create-an-mfc-application"></a>Создание приложения MFC

1. На **файл** последовательно выберите пункты **New** и выберите **проекта**.

2. В **новый проект** в левой области в разделе диалогового **установленные шаблоны**, разверните **Visual C++** , а затем выберите **MFC**. В средней области выберите **приложение MFC**. В **имя** введите *MFCD2DWalkthrough*. Нажмите кнопку **ОК**.

3. В **мастер приложений MFC**, выберите **Готово** без изменения любых параметров.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Создание кисти сплошного цвета и кисти линейного градиента

1. В **обозревателе решений**в **MFCD2DWalkthrough** проекта **файлы заголовков** папку, откройте MFCD2DWalkthroughView.h. Добавьте следующий код в `CMFCD2DWalkthroughView` класса, чтобы создать три переменных с данными:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Сохраните файл и закройте его.

2. В **исходные файлы** папку, откройте MFCD2DWalkthroughView.cpp. В конструкторе для `CMFCD2DWalkthroughView` класса, добавьте следующий код:

   ```cpp
   // Enable D2D support for this window:
   EnableD2DSupport();

   // Initialize D2D resources:
   m_pBlackBrush = new CD2DSolidColorBrush(
       GetRenderTarget(),
       D2D1::ColorF(D2D1::ColorF::Black));

   m_pTextFormat = new CD2DTextFormat(
       GetRenderTarget(),
       _T("Verdana"),
       50);

   m_pTextFormat->Get()->SetTextAlignment(
       DWRITE_TEXT_ALIGNMENT_CENTER);

   m_pTextFormat->Get()->SetParagraphAlignment(
       DWRITE_PARAGRAPH_ALIGNMENT_CENTER);

   D2D1_GRADIENT_STOP gradientStops[2];

   gradientStops[0].color =
       D2D1::ColorF(D2D1::ColorF::White);

   gradientStops[0].position = 0.f;
   gradientStops[1].color =
       D2D1::ColorF(D2D1::ColorF::Indigo);

   gradientStops[1].position = 1.f;

   m_pLinearGradientBrush = new CD2DLinearGradientBrush(
       GetRenderTarget(),
       gradientStops,
       ARRAYSIZE(gradientStops),
       D2D1::LinearGradientBrushProperties(
           D2D1::Point2F(0,0),
           D2D1::Point2F(0,0)));
   ```

   Сохраните файл и закройте его.

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Чтобы изменить градиентной кисти, чтобы она изменялась в соответствии с изменением размера окна

1. На **проекта** меню, выберите **мастер классов**.

2. В **мастер классов MFC**в разделе **имя класса**выберите `CMFCD2DWalkthroughView`.

3. На **сообщений** вкладке **сообщений** выберите `WM_SIZE` и выберите **добавить обработчик**. Это действие добавляет `OnSize` обработчик сообщений для `CMFCD2DWalkthroughView` класса.

4. В **существующие обработчики** выберите `OnSize`. Выберите **изменить код** для отображения `CMFCD2DWalkthroughView::OnSize` метод. В конце метода добавьте следующий код.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Сохраните файл и закройте его.

## <a name="to-implement-a-d2d-drawing-handler"></a>Реализация обработчика рисования D2D

1. На **проекта** меню, выберите **мастер классов**.

2. В **мастер классов MFC**в разделе **имя класса**выберите `CMFCD2DWalkthroughView`.

3. На **сообщений** выберите **добавить настраиваемое сообщение**.

4. В **добавить настраиваемое сообщение** диалогового **настраиваемое сообщение Windows** введите *AFX_WM_DRAW2D*. В **имя обработчика сообщения** введите *OnDraw2D*. Выберите **зарегистрированное сообщение** и затем выберите **ОК**. Это действие добавляет обработчик сообщений для сообщения AFX_WM_DRAW2D `CMFCD2DWalkthroughView` класса.

5. В **существующие обработчики** выберите `OnDraw2D`. Выберите **изменить код** для отображения `CMFCD2DWalkthroughView::OnDraw2D` метод. Используйте следующий код для `CMFCD2DWalkthroughView::OnDrawD2D` метод:

   ```cpp
   afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(
       WPARAM wParam,
       LPARAM lParam)
   {
       CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;
       ASSERT_VALID(pRenderTarget);

       CRect rect;
       GetClientRect(rect);

       pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);

       pRenderTarget->DrawText(
           _T("Hello, World!"),
           rect,
           m_pBlackBrush,
           m_pTextFormat);

       return TRUE;
   }
   ```

   Сохраните файл и закройте его.

## <a name="to-verify-the-results"></a>Проверка результатов

- Выполните сборку и запуск приложения. Он должен иметь прямоугольник с градиентной заливкой, которое изменяется при изменении размера окна. «Hello World!» должны отображаться в центре прямоугольника.

## <a name="see-also"></a>См. также

- [Пошаговые руководства](../mfc/walkthroughs-mfc.md)
