---
title: Создание приложения MFC
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: df1e49ffe9e4350d2023bc471d3687bec5defa04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434610"
---
# <a name="creating-an-mfc-application"></a>Создание приложения MFC

Приложение MFC является исполняемым приложением для Windows на основе библиотеки Microsoft Foundation Class (MFC). Наиболее простым способом создания приложения MFC является использование мастера приложений MFC.

> [!IMPORTANT]
>  Проекты MFC не поддерживаются в выпусках Visual Studio Express.

Исполняемыми приложениями MFC обычно делятся на пять типов: стандартные приложения Windows, диалоговые окна, приложений на основе форм, приложений в стиле проводника и стиле браузера веб-приложений. Дополнительные сведения:

- [Использование классов для создания приложений Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [Создание и отображение диалоговых окон](../../mfc/creating-and-displaying-dialog-boxes.md)

- [Создание приложений MFC на основе форм](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Создание приложения MFC в стиле проводника](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Создание приложения MFC в стиле браузера](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

Мастер приложений MFC создает соответствующие классы и файлы для приложений любого типа в зависимости от параметров, выбранных в мастере.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>Создание приложения MFC при помощи мастера приложений MFC.

1. Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).

1. В **новый проект** выберите **приложения MFC** в области «Шаблоны», чтобы открыть мастер.

1. Задайте параметры приложения с помощью [мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md).

    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.

1. Нажмите кнопку **Готово** закрыть мастер и открыть проект в среде разработки.

После создания проекта можно просмотреть файлы, созданные в **обозревателе решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Страницы свойств](../../ide/property-pages-visual-cpp.md)

