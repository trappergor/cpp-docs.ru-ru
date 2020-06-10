---
title: Создание окон фрейма документа
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
ms.openlocfilehash: e15a2a6bc016bf23bc0decf529b4c3ffeecc3a4c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621951"
---
# <a name="creating-document-frame-windows"></a>Создание окон фрейма документа

[Создание документа/представления](document-view-creation.md) показывает, как объект [CDocTemplate](reference/cdoctemplate-class.md) управляет созданием окна фрейма, документом и представлением, а также подключением друг к другу. Три аргумента [крунтимекласс](reference/cruntimeclass-structure.md) для `CDocTemplate` конструктора определяют классы фрейма, документа и представления, которые шаблон документа динамически создает в ответ на пользовательские команды, такие как команда создать в меню файл или команда создать окно в меню окна MDI. Шаблон документа хранит эти сведения для последующего использования при создании окна фрейма для представления и документа.

Чтобы механизм [RUNTIME_CLASS](reference/run-time-object-model-services.md#runtime_class) правильно работал, производные классы окон кадров должны быть объявлены с помощью макроса [DECLARE_DYNCREATE](reference/run-time-object-model-services.md#declare_dyncreate) . Это обусловлено тем, что платформа должна создавать окна фрейма документа, используя механизм динамического создания класса `CObject` .

Когда пользователь выбирает команду, которая создает документ, платформа вызывает шаблон документа, чтобы создать объект документа, его представление и окно фрейма, в котором будет отображаться представление. При создании окна фрейма документа шаблон документа создает объект соответствующего класса — класс, производный от [CFrameWnd](reference/cframewnd-class.md) для приложения SDI или [CMDICHILDWND](reference/cmdichildwnd-class.md) для приложения MDI. Затем платформа вызывает функцию-член [лоадфраме](reference/cframewnd-class.md#loadframe) объекта фрейма для получения сведений о создании из ресурсов и для создания окна Windows. Платформа присоединяет маркер окна к объекту фреймового окна. Затем он создает представление в виде дочернего окна окна фрейма документа.

Будьте внимательны при принятии решения о [том, когда следует инициализировать](when-to-initialize-cwnd-objects.md) `CWnd` объект, производный от.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Наследование класса от CObject (его динамический механизм создания)](deriving-a-class-from-cobject.md)

- [Создание документа/представления (шаблоны и создание окна фрейма)](document-view-creation.md)

- [Уничтожение окон фрейма](destroying-frame-windows.md)

## <a name="see-also"></a>См. также раздел

[Использование окон фрейма](using-frame-windows.md)
