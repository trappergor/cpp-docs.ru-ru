---
title: Общая последовательность создания окна
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: fb10ced78e230316a6e2982f24c1fb6e2e52ed8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364270"
---
# <a name="general-window-creation-sequence"></a>Общая последовательность создания окна

При создании собственного окна, например окна ребенка, в фреймворке используется тот же процесс, что и описано в [документе/посмотреть создание.](../mfc/document-view-creation.md)

Во всех классах окон, предоставляемых МФЦ, используется [двухступенчатая конструкция.](../mfc/one-stage-and-two-stage-construction-of-objects.md) То есть, во время вызова **нового** оператора СЗ, конструктор выделяет и инициализирует объект СЗ, но не создает соответствующее окно Windows. Это делается после этого, вызывая функцию члена [Создания](../mfc/reference/cwnd-class.md#create) объекта окна.

Функция `Create` члена делает окно Windows `HWND` и хранит его в общедоступных данных объекта [m_hWnd.](../mfc/reference/cwnd-class.md#m_hwnd) `Create`обеспечивает полную гибкость по параметрам создания. Прежде `Create`чем звонить, вы можете зарегистрировать класс окон с глобальной функцией [AfxRegisterWndClass,](../mfc/reference/application-information-and-management.md#afxregisterwndclass) чтобы установить значок и стили класса для кадра.

Для окон кадра можно использовать функцию `Create`члена [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) вместо. `LoadFrame`делает окно Windows, используя меньше параметров. Он получает много значений по умолчанию из ресурсов, включая подпись кадра, значок, таблицу акселератора и меню.

> [!NOTE]
> Ваш значок, таблица акселератора и ресурсы меню должны иметь общий идентификатор ресурсов, **например, IDR_MAINFRAME,** чтобы они были загружены LoadFrame.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Объекты окон](../mfc/window-objects.md)

- [Регистрация окна "классы"](../mfc/registering-window-classes.md)

- [Уничтожение оконных объектов](../mfc/destroying-window-objects.md)

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>См. также раздел

[Создание Windows](../mfc/creating-windows.md)
