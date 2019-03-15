---
title: Создание проекта библиотеки DLL MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 6ddc32ac3a2de5993e6755df0cd9fc7d3546094e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814154"
---
# <a name="creating-an-mfc-dll-project"></a>Создание проекта библиотеки DLL MFC

Библиотека DLL MFC — это двоичный файл, который выступает в качестве общей библиотеки функций, которые могут использоваться одновременно несколькими приложениями. Самый простой способ создания проекта MFC DLL является использование мастера MFC DLL.

> [!NOTE]
>  Вид функций в интегрированной среде разработки может зависеть от текущих параметров или выпуска и могут отличаться от описанных в справке. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Чтобы создать проект библиотеки DLL MFC, с помощью мастера MFC DLL

1. Следуйте инструкциям в разделе справки [создайте проект консольного приложения C++](../../get-started/tutorial-console-cpp.md).

**Примечание** в **новый проект** выберите `MFC DLL` значок в области «Шаблоны», чтобы открыть мастер библиотек DLL MFC.

1. Задайте параметры приложения с помощью [параметры приложения](../../mfc/reference/application-settings-mfc-dll-wizard.md) странице [мастера MFC DLL](../../mfc/reference/mfc-dll-wizard.md).

    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.

1. Нажмите кнопку **Готово** закрыть мастер и откройте новый проект в **обозревателе решений**.

После создания проекта можно просмотреть файлы, созданные в **обозревателе решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>См. также

[Типы проектов Visual C++](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Страницы свойств](../../build/reference/property-pages-visual-cpp.md)

