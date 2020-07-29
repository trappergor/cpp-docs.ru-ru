---
title: Общая последовательность создания окна
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 63b5e0131642692d9372c148827a583f19114fb9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223165"
---
# <a name="general-window-creation-sequence"></a>Общая последовательность создания окна

При создании собственного окна, например дочернего окна, платформа использует практически тот же процесс, который описан в разделе [Создание документа или представления](document-view-creation.md).

Все классы окон, предоставляемые MFC, используют [конструкцию с двумя этапами](one-stage-and-two-stage-construction-of-objects.md). То есть при вызове **`new`** оператора C++ конструктор выделяет и инициализирует объект c++, но не создает соответствующее окно Windows. Это можно сделать, вызвав функцию [создания](reference/cwnd-class.md#create) члена объекта Window.

`Create`Функция – член делает окно Windows и сохраняет его `HWND` в общедоступных элементах данных объекта C++ [m_hWnd](reference/cwnd-class.md#m_hwnd). `Create`обеспечивает полную гибкость по сравнению с параметрами создания. Перед вызовом `Create` может потребоваться зарегистрировать класс окна с глобальной функцией [афксрегистервндкласс](reference/application-information-and-management.md#afxregisterwndclass) , чтобы задать стили значков и классов для фрейма.

Для окон фрейма можно использовать функцию члена [лоадфраме](reference/cframewnd-class.md#loadframe) вместо `Create` . `LoadFrame`позволяет окну Windows использовать меньше параметров. Он получает множество значений по умолчанию из ресурсов, включая заголовок фрейма, значок, таблицу сочетаний клавиш и меню.

> [!NOTE]
> Ресурсы "значок", "Таблица сочетаний клавиш" и "меню" должны иметь общий идентификатор ресурса, например **IDR_MAINFRAME**, чтобы их можно было загрузить с помощью лоадфраме.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Объекты окон](window-objects.md)

- [Регистрация окна "классы"](registering-window-classes.md)

- [Уничтожение объектов окон](destroying-window-objects.md)

- [Создание окон фрейма документа](creating-document-frame-windows.md)

## <a name="see-also"></a>См. также статью

[Создание Windows](creating-windows.md)
