---
title: 'Пошаговое руководство: Добавление объекта D2D в проект MFC | Документация Майкрософт'
ms.custom: ''
ms.date: 09/20/2018
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
ms.openlocfilehash: 6117b17421e37238c9bc585677eb7b0c8ed557fb
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169662"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>Пошаговое руководство. Добавление объекта D2D в проект MFC

В этом пошаговом руководстве учебные материалы добавить базовый Direct2D (D2D) для Visual C++, проект Microsoft Foundation Class Library (MFC), а затем постройте проект в приложение, которое выводит «Hello, world» на градиентным фоном.

Пошаговом руководстве показано, как выполнять следующие задачи:

- Создайте приложение MFC.

- Создайте кисть сплошного цвета и кисти линейного градиента.

- Измените градиентной кисти, таким образом, чтобы он изменится соответствующим образом при изменении размера окна.

- Реализация обработчика рисования D2D.

- Проверьте результаты.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства, необходимо установить Visual Studio, установленные с **разработка классических приложений C++** рабочей нагрузки и необязательный **Visual C++ MFC для x86 и x64** компонента.

## <a name="to-create-an-mfc-application"></a>Создание приложения MFC

1. На **файл** последовательно выберите пункты **New** и выберите **проекта**.

1. В **новый проект** диалоговое окно, в области слева в разделе **установленные шаблоны**, разверните **Visual C++** , а затем выберите **MFC**. В средней области выберите **приложения MFC**. В **имя** введите *MFCD2DWalkthrough*. Нажмите кнопку **ОК**.

1. В **мастер приложений MFC**, выберите **Готово** без изменения любых параметров.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Для создания кисти сплошного цвета и кисти линейного градиента

1. В **обозревателе решений**в **MFCD2DWalkthrough** проекта **файлы заголовков** папку, откройте MFCD2DWalkthroughView.h. Добавьте следующий код в `CMFCD2DWalkthroughView` создаваемого три переменные данных класса:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Сохраните файл и закройте его.

1. В **исходные файлы** папку, откройте MFCD2DWalkthroughView.cpp. В конструкторе для `CMFCD2DWalkthroughView` класса, добавьте следующий код:

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

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Чтобы изменить градиентной кисти, таким образом, чтобы он изменится соответствующим образом при изменении размера окна

1. На **проекта** меню, выберите **мастер классов**.

1. В **мастер классов MFC**в разделе **имя класса**выберите `CMFCD2DWalkthroughView`.

1. На **сообщений** на вкладке **сообщений** выберите `WM_SIZE` и выберите **добавить обработчик**. Это действие добавляет `OnSize` обработчик сообщений для `CMFCD2DWalkthroughView` класса.

1. В **существующие обработчики** выберите `OnSize`. Выберите **изменить код** для отображения `CMFCD2DWalkthroughView::OnSize` метод. В конце метода добавьте следующий код.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Сохраните файл и закройте его.

## <a name="to-implement-a-d2d-drawing-handler"></a>Для реализации обработчика рисования D2D

1. На **проекта** меню, выберите **мастер классов**.

1. В **мастер классов MFC**в разделе **имя класса**выберите `CMFCD2DWalkthroughView`.

1. На **сообщений** вкладке, выберите **Добавьте настраиваемое сообщение**.

1. В **Добавьте настраиваемое сообщение** отображаемое в диалоговом окне **настраиваемое сообщение Windows** введите *AFX_WM_DRAW2D*. В **имя обработчика сообщения** введите *OnDraw2D*. Выберите **зарегистрированное сообщение** а затем нажмите **ОК**. Это действие добавляет обработчик сообщений для сообщения AFX_WM_DRAW2D `CMFCD2DWalkthroughView` класса.

1. В **существующие обработчики** выберите `OnDraw2D`. Выберите **изменить код** для отображения `CMFCD2DWalkthroughView::OnDraw2D` метод. Используйте этот код для `CMFCD2DWalkthroughView::OnDrawD2D` метод:

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

Выполните сборку и запуск приложения. Оно должно включать прямоугольник с градиентной заливкой, которое изменяется при изменении размера окна. «Hello World!» должны отображаться по центру прямоугольника.

## <a name="see-also"></a>См. также

[Пошаговые руководства](../mfc/walkthroughs-mfc.md)
