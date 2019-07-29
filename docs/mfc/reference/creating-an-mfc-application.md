---
title: Создание приложения MFC
ms.date: 07/28/2019
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 454a994da6db2841317d41ea1cdacfd36b0705e4
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606478"
---
# <a name="creating-an-mfc-application"></a>Создание приложения MFC

Приложение MFC является исполняемым приложением для Windows на основе библиотеки Microsoft Foundation Class (MFC). Самый простой способ создать приложение MFC — использовать мастер приложений MFC (**проект приложения MFC** в Visual Studio 2019). Чтобы создать консольное приложение MFC, используйте мастер рабочего стола Windows и выберите параметры **консольное приложение** и **MFC** .

> [!IMPORTANT]
>  Проекты MFC не поддерживаются в выпусках Visual Studio Express.

Исполняемые файлы MFC обычно делятся на пять типов: стандартные приложения Windows, диалоговые окна, приложения на основе форм, приложения в стиле обозревателя и приложения в стиле веб-браузера. Дополнительные сведения:

- [Использование классов для написания приложений Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [Создание и отображение диалоговых окон](../../mfc/creating-and-displaying-dialog-boxes.md)

- [Создание приложений MFC на основе форм](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Создание приложения MFC в стиле проводника](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Создание приложения MFC в стиле браузера](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

Мастер приложений MFC создает соответствующие классы и файлы для приложений любого типа в зависимости от параметров, выбранных в мастере.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>Создание приложения MFC при помощи мастера приложений MFC.

1. Следуйте инструкциям, приведенным в разделе справки [Создание C++ проекта консольного приложения](../../get-started/tutorial-console-cpp.md).

1. В диалоговом окне **Новый проект** в области Шаблоны выберите пункт **приложение MFC** , чтобы открыть мастер.

1. Определите параметры приложения с помощью [мастера приложений MFC](../../mfc/reference/mfc-application-wizard.md).

    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.

1. Нажмите кнопку **Готово** для завершения работы мастера и откройте новый проект в среде разработки.

После создания проекта можно просмотреть его файлы при помощи **обозревателя решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Страницы свойств](../../build/reference/property-pages-visual-cpp.md)

