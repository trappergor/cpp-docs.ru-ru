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
ms.openlocfilehash: 6a1718e1f347be46b2f228479d3dbd30027b3160
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077446"
---
# <a name="creating-an-mfc-dll-project"></a>Создание проекта библиотеки DLL MFC

Библиотека DLL MFC — это двоичный файл, который выступает в качестве общей библиотеки функций, которые могут одновременно использоваться несколькими приложениями. Самый простой способ создать проект библиотеки DLL MFC — использовать мастер DLL MFC.

> [!NOTE]
>  Внешний вид функций в интегрированной среде разработки может зависеть от текущих параметров или выпуска и может отличаться от описанных в справке. Чтобы изменить параметры, выберите **Импорт и экспорт параметров** в меню **Сервис** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Создание проекта библиотеки DLL MFC с помощью мастера библиотек DLL MFC

1. Следуйте инструкциям в разделе справки по [созданию приложения MFC](creating-an-mfc-application.md) , но в списке доступных шаблонов выберите **Библиотека динамической компоновки MFC** или библиотека **DLL MFC** .

1. Определите параметры приложения на странице [Параметры приложения](../../mfc/reference/application-settings-mfc-dll-wizard.md) [мастера библиотек DLL MFC](../../mfc/reference/mfc-dll-wizard.md).

    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.

1. Нажмите кнопку **Готово** , чтобы закрыть мастер и открыть новый проект в **Обозреватель решений**.

После создания проекта можно просмотреть его файлы при помощи **обозревателя решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>См. также:

[Типы проектов C++ в Visual Studio](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Страницы свойств](../../build/reference/property-pages-visual-cpp.md)
