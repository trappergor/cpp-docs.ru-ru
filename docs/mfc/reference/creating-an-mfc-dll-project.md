---
title: Создание проекта библиотеки DLL MFC
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 6367b2a4b85b2c586c5a4420a8be1f80d334b2e4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363964"
---
# <a name="creating-an-mfc-dll-project"></a>Создание проекта библиотеки DLL MFC

MFC DLL — это двоичный файл, который действует как общая библиотека функций, которые могут использоваться одновременно несколькими приложениями. Самый простой способ создать проект MFC DLL – использовать MFC DLL Wizard.

> [!NOTE]
> Появление функций в IDE может зависеть от ваших активных настроек или изданий и может отличаться от тех, которые описаны в Справке. Чтобы изменить параметры, выберите **Импорт и экспорт параметров** в меню **Сервис** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Для создания проекта MFC DLL с использованием MFC DLL Wizard

1. Следуйте инструкциям в теме справки [Создание приложения MFC,](creating-an-mfc-application.md) но выберите **MFC Dynamic Link Library** или **MFC DLL** из списка доступных шаблонов.

1. Определите настройки приложения, используя страницу [настроек приложения](../../mfc/reference/application-settings-mfc-dll-wizard.md) [MFC DLL Wizard.](../../mfc/reference/mfc-dll-wizard.md)

    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.

1. Нажмите **Закончить,** чтобы закрыть мастера и открыть свой новый проект в **Solution Explorer**.

После создания проекта можно просмотреть его файлы при помощи **обозревателя решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>См. также раздел

[Типы проектов C++ в Visual Studio](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Страницы свойств](../../build/reference/property-pages-visual-cpp.md)
